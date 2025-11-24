Testing gromacs-vanilla
------------------------
 
The tests described in the following tables were performed on __November 24, 2025__ to test whether the interface between gromacs-vanilla and the master version of PLUMED is working correctly.

WARNING: gromacs-vanilla does not pass the energy to PLUMED 

## Basic functionalities

| Description of test | Status | 
|:--------------------|:------:| 
| MD code number of atoms passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](natoms_master.html) |
| MD code positions passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](positions_master.html) |
| MD code cell vectors passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](cell_master.html) |
| MD timestep passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](timestep_master.html) |
| MD code masses passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](mass_master.html) |
| MD code charges passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](charge_master.html) |
| PLUMED forces passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](forces_master.html) |

## Tests on virial

| Description of test | Status | 
|:--------------------|:------:| 
| PLUMED virial passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%201%25-green.svg)](virial_master.html) |
