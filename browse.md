## Browse the tests  
   
The codes listed below below were tested on __January 05, 2025__.
PLUMED-TESTCENTER tested whether the current and development versions of the code can be used to complete the tests for each of these codes.



| Name of Program  | Short description | Compiles | Passes tests |
|:-----------------|:------------------|:--------:|:------------:|
| [gromacs](https://www.gromacs.org) | A free and open-source software suite for high-performance molecular dynamics and output analysis. |  [![tested on v2.10](https://img.shields.io/badge/v2.10-passing-green.svg)](tests/gromacs/install.html) [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](tests/gromacs/install.html) |  [![tested on v2.10](https://img.shields.io/badge/v2.10-failed-red.svg)](tests/gromacs/testout_v2.10.html) [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](tests/gromacs/testout_master.html) | 
| [gromacs-vanilla](https://www.gromacs.org) | A free and open-source software suite for high-performance molecular dynamics and output analysis. Form the 2025 comes with a feature-reduced version of the plumed patch |  [![tested on v2.10](https://img.shields.io/badge/v2.10-passing-green.svg)](tests/gromacs-vanilla/install.html) [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](tests/gromacs-vanilla/install.html) |  [![tested on v2.10](https://img.shields.io/badge/v2.10-failed-red.svg)](tests/gromacs-vanilla/testout_v2.10.html) [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](tests/gromacs-vanilla/testout_master.html) | 
| [i-pi](https://ipi-code.org) | A universal force engine interface that can be used to sample thermodynamic ensembles once it is coupled with a function for calculating the energies and forces |  [![tested on v2.10](https://img.shields.io/badge/v2.10-passing-green.svg)](tests/i-pi/install.html) [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](tests/i-pi/install.html) |  [![tested on v2.10](https://img.shields.io/badge/v2.10-broken-36454F.svg)](tests/i-pi/testout_v2.10.html) [![tested on master](https://img.shields.io/badge/master-broken-36454F.svg)](tests/i-pi/testout_master.html) | 
| [lammps](https://www.lammps.org) | The Large-scale Atomic/Molecular Massively Parallel Simulator. An MD code that is often used for materials modelling. |  [![tested on v2.10](https://img.shields.io/badge/v2.10-failed-red.svg)](tests/lammps/install.html) [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](tests/lammps/install.html) |  [![tested on v2.10](https://img.shields.io/badge/v2.10-broken-36454F.svg)](tests/lammps/testout_v2.10.html) [![tested on master](https://img.shields.io/badge/master-broken-36454F.svg)](tests/lammps/testout_master.html) | 
| [quantum_espresso](https://www.quantum-espresso.org) | An integrated suite of Open-Source computer codes for electronic-structure calculatiosn and materials modelling at the nanoscales that uses density-functional theory, plane waves and pseudopotentials. |  [![tested on v2.10](https://img.shields.io/badge/v2.10-passing-green.svg)](tests/quantum_espresso/install.html) [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](tests/quantum_espresso/install.html) |  [![tested on v2.10](https://img.shields.io/badge/v2.10-failed-red.svg)](tests/quantum_espresso/testout_v2.10.html) [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](tests/quantum_espresso/testout_master.html) | 
| [simplemd](https://www.plumed.org/doc-master/user-doc/html/simplemd.html) | A Lennard Jones molecular dynamics code that is part of PLUMED. |  [![tested on v2.10](https://img.shields.io/badge/v2.10-passing-green.svg)](tests/simplemd/install.html) [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](tests/simplemd/install.html) |  [![tested on v2.10](https://img.shields.io/badge/v2.10-passing-green.svg)](tests/simplemd/testout_v2.10.html) [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](tests/simplemd/testout_master.html) | 



#### Building PLUMED

When the tests above are run PLUMED is built using the install plumed action.
```yaml
- name: Install plumed
      uses: Iximiel/install-plumed@v1
      with:
         CC: "ccache mpicc"
         CXX: "ccache mpic++"
         suffix: "${{ steps.get-key.outputs.suffix }}"
         version: "${{ steps.get-key.outputs.branch }}"
         extra_options: --enable-boost_serialization --enable-fftw --enable-libtorch LDFLAGS=-Wl,-rpath,$LD_LIBRARY_PATH --disable-basic-warnings
```

