Testing simplemd
------------------------
 
The tests described in the following table were performed on __June 27, 2024__ to test whether the interface between simplemd and the master version of PLUMED is working correctly.

WARNING: simplemd does not pass the virial to PLUMED and it is thus not possible to run NPT simulations with this code

| Description of test | Status | 
|:--------------------|:------:| 
| MD code number of atoms passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](natoms_master.html) |
| MD code positions passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](positions_master.html) |
| MD code cell vectors passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](cell_master.html) |
| MD timestep passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](timestep_master.html) |
| MD code masses passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](mass_master.html) |
| PLUMED forces passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%203%25-green.svg)](forces_master.html) |
| MD code potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](energy_master.html) |
| PLUMED forces on potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](engforce_master.html) |
