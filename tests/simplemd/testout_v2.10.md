Testing simplemd
------------------------
 
The tests described in the following tables were performed on __November 24, 2025__ to test whether the interface between simplemd and the v2.10 version of PLUMED is working correctly.

WARNING: simplemd does not pass the virial to PLUMED and it is thus not possible to run NPT simulations with this code

## Basic functionalities

| Description of test | Status | 
|:--------------------|:------:| 
| MD code number of atoms passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](natoms_v2.10.html) |
| MD code positions passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](positions_v2.10.html) |
| MD code cell vectors passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](cell_v2.10.html) |
| MD timestep passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](timestep_v2.10.html) |
| MD code masses passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](mass_v2.10.html) |
| PLUMED forces passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%203%25-green.svg)](forces_v2.10.html) |


## Tests on energy

| Description of test | Status | 
|:--------------------|:------:| 
| MD code potential energy passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](energy_v2.10.html) |
| PLUMED forces on potential energy passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](engforces_v2.10.html) |
