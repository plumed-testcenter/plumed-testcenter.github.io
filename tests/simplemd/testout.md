Testing simplemd
------------------------
 
The tests described in the following table were performed on __April 14, 2023__ to test whether the interface between simplemd and the v2.9 version of PLUMED is working correctly.

WARNING: simplemd does not pass the virial to PLUMED and it is thus not possible to run NPT simulations with this code

| Description of test | Status | 
|:--------------------|:------:| 
| MD code number of atoms passed correctly | [![tested on v2.9](https://img.shields.io/badge/v2.9-passing-green.svg)](natoms_v2.9.html)| 
| MD code positions passed correctly | [![tested on v2.9](https://img.shields.io/badge/v2.9-passing-green.svg)](positions_v2.9.html)| 
| MD code cell vectors passed correctly | [![tested on v2.9](https://img.shields.io/badge/v2.9-passing-green.svg)](cell_v2.9.html) | 
| MD timestep passed correctly | [![tested on v2.9](https://img.shields.io/badge/v2.9-passing-green.svg)](timestep_v2.9.html) | 
| MD code masses passed correctly | [![tested on v2.9](https://img.shields.io/badge/v2.9-passing-green.svg)](mass_v2.9.html) | 
| PLUMED forces passed correctly | [![tested on v2.9](https://img.shields.io/badge/v2.9-passing-green.svg)](forces_v2.9.html) | 
| MD code potential energy passed correctly | [![tested on v2.9](https://img.shields.io/badge/v2.9-passing-green.svg)](energy_v2.9.html) | 
| PLUMED forces on potential energy passed correctly | [![tested on v2.9](https://img.shields.io/badge/v2.9-failed-red.svg)](engforce_v2.9.html) | 
