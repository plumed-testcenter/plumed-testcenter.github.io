# How to contribute tests to the PLUMED-TESTCENTER

You can add your own MD code to the PLUMED-TESTCENTER.
If you do so this website will then test the interface between PLUMED and your MD code once a week.
The results from these tests will then be displayed on [the dashboard](browse.md).
To build your tests you will need to collect together the input files that will allow you to generate a trajectory with your MD code and PLUMED.
These input files should be gathered together and added to the plumed-testcenter repository in a directory called:

```
tests/<your code name>/input
```

You will then need to write three further files in `tests/<your code name>`

* `install.sh` - A shell script that downloads and installs a version of your MD code patched with PLUMED 
* `info.yml` - A yaml file with basic information on your MD code including what tests should be performed
* `mdcode.py` - A python class that tells the testcenter how to run your MD code and how to get various outputs from you code to compare with output from PLUMED.

You are well advised to look the versions of these files that have been written for testing other codes.
In the sections that follow we will try to provide some rationale that explains the content of the three files described above.

Lastly, you will need to modify the line:

```yaml
        replica: ["simplemd", "lammps", "quantum_espresso"]
```
to:
```yaml
        replica: ["simplemd", "lammps", "quantum_espresso", "<your code name>"]
```

in the file `.github/workflows/main.yml` to add your code to the list of those that are tested here.
Use the same name of the directory where you put your code into.
The order is not important and the codes will be alphabetically organized in [the dashboard](browse.md).

## Writing an install.sh file

The `install.sh` that you will write to download and install your code must be written in bash and will have a structure something like the one shown below:

```bash
# Add code here to download your code from some repository 

# Add code here to build your code so that final executible is in $HOME/opt/bin

```

Notice that a part of the final install script that is used for all MD codes is contained in the file `tests/script_head`.
This file contains the `#!/bin/bash` that appears at the top of any bash script.
This file also sets the values of three bash variables that you will need to use when you install your code:

1. `mode` - the mode that is used to link PLUMED.
2. `suffix` - the version of PLUMED we are linking to is called plumed$suffix.
3. `basedir` - essentially the directory that we are running within.

Once your install.sh script has run a test is performed to determine if an executible with the name given in the `info.yml` file has been created in `$(HOME)/opt/bin`.
This test is performed by the bash script `tests/check_status.sh`.
This script tells the python script (`build.py`) that constructs
[the dashboard page](browse.md) whether or not your code compiled sucessfully so that the appropriate badges can be put on the dashboard.
Notice that this information is transferred by adding lines to the `info.yml` file for your code.

## Running your code from python

As explained above the `mdcode.py` file that you must contains a class with functions that serve two purposes:

1. There are functions that allow the testcenter codes to run your MD code from a python script and thus test PLUMED.
2. There are functions that recover various quantities from the output files that your code generates for comparison with the output with PLUMED.

In this section we will cover the functions that perform thee first set of operations; namely, the functions `setParams` and `runMD`.
For the tests of `simplemd` (the MD code that is part of PLUMED) these two functions look like this:

```python
class mdcode :
  def setParams( self ) :
       params = {
         "temperature": 1.0,
         "tstep": 0.005,
         "relaxtime": 1.0,
         "pressure": 1.0,
         "prelaxtime": 4
       }
       return params

  def runMD( self, mdparams ) :
       # Prepare a string that contains the input for simplemd
       inp = "inputfile input.xyz\n"
       inp = inp + "outputfile output.xyz\n"
       inp = inp + "temperature " + str(mdparams["temperature"]) + "\n"
       inp = inp + "tstep " + str(mdparams["tstep"]) + "\n"
       inp = inp + "" + str(1/mdparams["relaxtime"]) + "\n"
       inp = inp + "forcecutoff 2.5\n"
       inp = inp + "listcutoff  3.0\n"
       inp = inp + "nstep " + str(mdparams["nsteps"]) + "\n"
       inp = inp + "nconfig 1 trajectory.xyz\n"
       inp = inp + "nstat   1 energies.dat\n"
       of=open("in","w+")
       of.write(inp)
       of.close()
       # Code to deal with restraint 
       if "restraint" in mdparams and mdparams["restraint"]>0 :
          f = open("plumed.dat","w+")
          f.write("dd: DISTANCE ATOMS=1,2 \nRESTRAINT ARG=dd KAPPA=2000 AT=" + str(mdparams["restraint"]) + "\nPRINT ARG=dd FILE=colvar FMT=%8.4f\n")
          f.close()
       # Work out the name of the plumed executable 
       executible = mdparams["executible"]
       cmd = [executible, "simplemd"]
       # Now run the calculation using subprocess
       with open("stdout","w") as stdout:
        with open("stderr","w") as stderr:
           plumed_out = subprocess.run(cmd, text=True, input=inp, stdout=stdout, stderr=stderr )
       return plumed_out.returncode 
```

To run the tests on your MD code the testcenter codes needs to be able to adjust the following parameters.
It does this by passing a dictionary called `mdparams` to the function `runMD`.
 This function then creates an input file from the information in `mdparams` and runs the calculation with your MD code. 
The key parameters that are passed within the `mdparams` are:

* __ensemble__ - either npt or nvt. If this variable is npt then the calculation should be run at constant pressure. If it is nvt then the calculation should be run at constant volume. If there is not a barostat in your code you can safely ignore this variable and run everything with nvt (as is done for simplemd in the example above). If you set the tests correctly (see next section) you will not be testing any features that require you to run at constant pressure.
* __temperature__ - the temperature 
* __relaxtime__ - the thermostat relaxation time.
* __pressure__ - the pressure  
* __prelaxtime__ - the barstat relaxation time.
* __tstep__ - the integration timestep
* __nsteps__ - the number of steps of MD to perform
* __restraint__ - this parameter is used to test that PLUMED is applying forces on atoms correctly. If the value passed in this variable is positive then this should be used as the $d_0$ parameter of a harmonic restraint with the form $\frac{1}{2}\kappa(d_{12} - d_0)^2$, where $d_{12}$ is the distance between the first two atoms in your system and $\kappa = 2000 kJ mol$^{-1}$ nm$^{-2}$. In the example above with simplemd this restraint is applied by PLUMED (because simplemd has no functionality of its own to apply a restraint of this form). In most other MD codes you should be able to apply the harmonic restraint within the MD code. The test here then determines whether the time series of distances that is returned when the restraint is applied by PLUMED is the same as the time series that is returned when the restraint is applied within the MD code.
* __executible__ - the name of the MD codes executible. This is necessary as we test the interface between each code, the latest stable version of PLUMED and the master version of PLUMED. Two versions of each MD code (with different names) are thus compiled and tested. The name of the executible that is to be tested is controlled by the underlying code plumed testcenter code.

Notice that although some of these variables (e.g. nsteps) are set by the underlying plumed testcenter code, there are others that must be given sensible initial values.
This process of giving sensible initial values to variables is done by `setParams`.
Parameters here should be set in the units of the MD code (and not in PLUMED units).
Importantly, however, __the pressure must be set equal to 1 bar in whatever internal units your MD code employs__ as we assume that the pressure has been set to 1 bar when we test the virial.

## Writing your info.yml file

The `info.yml` file does two things:

1. It provides some basic information about your code
2. It tells the code that forms part of the test center what tests should be performed.

To understand these two functions it is instructive to look at an example of this file.
Below is the `info.yml` file that is used when we test quantum\_espresso:

```yml
name: Quantum ESPRESSO
description: An integrated suite of Open-Source computer codes for electronic-structure calculatiosn and materials modelling at the nanoscales that uses density-functional theory, plane waves and pseudopotentials.
executible: pw
link: https://www.quantum-espresso.org
tests:
   positions: yes
   timestep: yes
   mass: yes
   charge: no
   forces: no
   virial: no
   energy: yes
```

The first four lines in the file do task (1).
These first four lines are hopefully self-explanatory.

The remainder of the file complete task (2).
There are essentially seven tests we can perform on an MD code:

1. __positions__ - are the number of atoms, the positions of the atoms and the cell vectors correctly passed from the MD code to PLUMED. This test should always be performed.
2. __timestep__ - is the integration timestep correctly passed to PLUMED. This test should always be performed.
3. __masses__ - are the masses of the atoms correctly passed to PLUMED. This test should always be performed.
4. __charges__ - are the charges of the atosm correctly passed to PLUMED (N.B. we mean charges on classical ions here so it makes no sense to do this test for Quantum Espresso).
5. __forces__ - if we apply a harmonic restraint on the distance between atom 1 and atom 2 using PLUMED and using the MD code do we obtain the same time series of distances between atoms 1 and 2. Obviously, you have to be able to apply a harmonic restraint using the MD code to do this test.
6. __virial__ - can we compensate for a restraint that PLUMED applies on the volume by adjusting the pressure at which we run the simulation. You cannot do this test if your code cannot run npt simulations.
7. __energy__ - is the potential energy correctly passed from the MD code to PLUMED. Obviously it only makes sense to perform this test if you have written code to pass the potential energy from the MD code to PLUMED.

Two further tests are then done based on the values of the keywords:

1. If __forces__ and __energy__ are set to yes then we test whether PLUMED can set forces on the energy correctly in a simulation run in the nvt ensemble.
2. If __virial__ and __energy__ are set to yes then we test whether PLUMED can set forces on the energy correctly in a simulation run in the npt ensemble.

## Recovering data from the MD code for comparison

Having described the tests that are performed by the testcenter we can now describe the other functions that must be written in the `mdcode.py` file. These functions recover various quantities from the MD code so that a comparison can be performed between the values that are passed to PLUMED and the values that the MD code outputs. The various functions you need to write are described in the code snippet below:

```python
class mdcode :
   def getTimestep( self ) -> float:
       # Return the timestep that was used in your MD simulations in ps 
       # as a single float.

   def getNumberOfAtoms( self, rundir ) -> list:
       # Return a list that contains the number of atoms in each of the frames of the trajectory that 
       # was run in the directory rundir. Normally you would read in the trajectory file that your 
       # code output. This file is in rundir. You then return a list that has a length equal to 
       # the number of frames in this trajectory. Each of the numbers in this list is then the number 
       # of atoms. All these numbers of atoms in your list will likely be the same.

   def getPositions( self, rundir ) -> np.ndarray:
       # Return a NumPy array that contains the trajectory for each of the atoms. This function is called
       # after your MD code has run a MD calculation in which the positions of m atoms have been propegated for 
       # n steps in the directory rundir. There should, therefore, be a trajectory in rundir that contains the positions
       # the atoms took after each of these n steps. This function should read in that trajectory and concatenate all the data 
       # within it into an n*m by 3 array of atomic positions. All the positions in this array should be given in units of nm.

   def getCell( self, rundir ) -> np.ndarray:
       # Return a NumPy array that contains the cell vectors for each frame of a trajectory. This function is called
       # after your MD code has run a MD calculation in which the positions of m atoms have been propegated for 
       # n steps in the directory rundir. There should, therefore, be a trajectory in rundir that contains the positions
       # the atoms took after each of these n steps. This function should read in the cell vectors from that trajectory and return 
       # an n by 9 array of cell vectors. All the vectors in this array should be given in units of nm.

   def getMasses( self, rundir ) -> np.ndarray:
       # Return a NumPy array that contains the masses of each of the m atoms in the system. This function is called
       # after your MD code has run a MD calculation in which the positions of m atoms have been propegated for
       # n steps in the directory rundir. You can read the masses of the atoms from one of the output files in this directory 
       # or you can read them from the input files.

   def getCharges( self, rundir ) -> np.ndarray:
       # Return a NumPy array that contains the charges of each of the m atoms in the system. This function is called
       # after your MD code has run a MD calculation in which the positions of m atoms have been propegated for
       # n steps in the directory rundir. You can read the charges of the atoms from one of the output files in this directory 
       # or you can read them from the input files.

   def getEnergy( self, rundir ) -> np.ndarray:
       # Return a NumPy array that contains the value of the potential energies that the sytem took. This function is called
       # after your MD code has run a MD calculation in which the positions of m atoms have been propegated for
       # n steps in the directory rundir. You should be able to read the potential energy of this ensemble of m atoms after each 
       # of these n steps from an output file. This function should read in those energies and return a list of n energies for comparison
       # with the energies that are output by PLUMED. All energies should be returned in units of kJ/mol. 
```

These functions are used in the tests on __positions__, __timestep__, __masses__, __charges__ and __energy__.
All other tests are general for all MD codes as we can use output from PLUMED.
