Number of atoms passed correctly
--------------------------------

PLUMED must receive the number of atoms that are being simulated from the MD code in order to calculate CVs correctly.  
To test this number is passed correctly to PLUMED we run a short trajectory and output the positions of all the atoms 
that are passed to PLUMED using the following command:

{% raw %}
<div class="plumedInputContainer">
<div class="plumedpreheader">
<div class="headerInfo" id="value_details_working1.dat"> Click on the labels of the actions for more information on what each action computes </div>
<div class="containerBadge">
<div class="headerBadge"><a href="working1.dat.plumed.stderr"><img src="https://img.shields.io/badge/2.10-passing-green.svg" alt="tested on2.10" /></a></div>
<div class="headerBadge"><a href="working1.dat.plumed_master.stderr"><img src="https://img.shields.io/badge/master-passing-green.svg" alt="tested onmaster" /></a></div>
</div>
</div>
<pre class="plumedlisting">
<span class="plumedtooltip" style="color:green">DUMPATOMS<span class="right">Dump selected atoms on a file. <a href="https://www.plumed.org/doc-master/user-doc/html/DUMPATOMS" style="color:green">More details</a><i></i></span></span> <span class="plumedtooltip">ATOMS<span class="right">the atom indices whose positions you would like to print out<i></i></span></span>=<span class="plumedtooltip">@mdatoms<span class="right">refers to all the MD codes atoms but not PLUMEDs vatoms. <a href="https://www.plumed.org/doc-master/user-doc/html/specifying_atoms">Click here</a> for more information. <i></i></span></span> <span class="plumedtooltip">FILE<span class="right">file on which to output coordinates; extension is automatically detected<i></i></span></span>=plumed.xyz
</pre></div>

 {% endraw %} 

# Trajectory

Input and output files for the test calculation are available inthis [zip archive](basic_v2.10.zip)

# Results

| MD code output | PLUMED output | Tolerance | % Difference | 
|:-------------|:--------------|:--------------|:--------------| 
| 256 | 256 | 0.01 | 0.0 |
| 256 | 256 | 0.01 | 0.0 |
| 256 | 256 | 0.01 | 0.0 |
| 256 | 256 | 0.01 | 0.0 |
| 256 | 256 | 0.01 | 0.0 |
| 256 | 256 | 0.01 | 0.0 |
| 256 | 256 | 0.01 | 0.0 |
| 256 | 256 | 0.01 | 0.0 |
| 256 | 256 | 0.01 | 0.0 |
| 256 | 256 | 0.01 | 0.0 |
| 256 | 256 | 0.01 | 0.0 |


The first two columns of the table below contains the number of atoms that were in the structure the MD trajectory started from and the number of atomic positions
that were output by the command above.  If the PLUMED interface is working correctly these two numbers should be identical. 


### Graphical representation (_beta_)
A visualization of the table above:  
![natoms_v2.10](./natoms_v2.10.png)
