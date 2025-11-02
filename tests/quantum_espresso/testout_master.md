Testing quantum_espresso
------------------------
 
The tests described in the following tables were performed on __November 02, 2025__ to test whether the interface between quantum_espresso and the master version of PLUMED is working correctly.

## Basic functionalities

| Description of test | Status | 
|:--------------------|:------:| 
| MD code number of atoms passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](natoms_master.html) |
| MD code positions passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](positions_master.html) |
| MD code cell vectors passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](cell_master.html) |
| MD timestep passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](timestep_master.html) |
| MD code masses passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](mass_master.html) |

## Tests on virial

| Description of test | Status | 
|:--------------------|:------:| 
| PLUMED virial passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](virial_master.html) |


## Tests on energy

| Description of test | Status | 
|:--------------------|:------:| 
| MD code potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](energy_master.html) |
| PLUMED forces on potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%2028%25-red.svg)](engforces_master.html) |
| PLUMED contribution to virial due to force on potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](engvir_master.html) |
