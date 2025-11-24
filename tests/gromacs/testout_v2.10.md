Testing gromacs
------------------------
 
The tests described in the following tables were performed on __November 24, 2025__ to test whether the interface between gromacs and the v2.10 version of PLUMED is working correctly.

## Basic functionalities

| Description of test | Status | 
|:--------------------|:------:| 
| MD code number of atoms passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](natoms_v2.10.html) |
| MD code positions passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](positions_v2.10.html) |
| MD code cell vectors passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](cell_v2.10.html) |
| MD timestep passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](timestep_v2.10.html) |
| MD code masses passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](mass_v2.10.html) |
| MD code charges passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](charge_v2.10.html) |

## Tests on virial

| Description of test | Status | 
|:--------------------|:------:| 
| PLUMED virial passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](virial_v2.10.html) |


## Tests on energy

| Description of test | Status | 
|:--------------------|:------:| 
| MD code potential energy passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%200%25-green.svg)](energy_v2.10.html) |
| PLUMED forces on potential energy passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%201348%25-red.svg)](engforces_v2.10.html) |
| PLUMED contribution to virial due to force on potential energy passed correctly | [![tested on v2.10](https://img.shields.io/badge/v2.10-fail%20985%25-red.svg)](engvir_v2.10.html) |
