Testing quantum_espresso
------------------------
 
The tests described in the following table were performed on __April 14, 2023__ to test whether the interface between quantum_espresso and the master version of PLUMED is working correctly.

| Description of test | Status | 
|:--------------------|:------:| 
| MD code number of atoms passed correctly | [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](natoms_master.html)| 
| MD code positions passed correctly | [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](positions_master.html)| 
| MD code cell vectors passed correctly | [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](cell_master.html) | 
| MD timestep passed correctly | [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](timestep_master.html) | 
| MD code masses passed correctly | [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](mass_master.html) | 
| PLUMED virial passed correctly | [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](virial_master.html) | 
| MD code potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](energy_master.html) | 
| PLUMED contribution to virial due to force on potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](engvir_master.html) | 
