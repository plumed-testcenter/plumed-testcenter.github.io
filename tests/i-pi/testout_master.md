Testing i-pi
------------------------
 
The tests described in the following table were performed on __December 29, 2024__ to test whether the interface between i-pi and the master version of PLUMED is working correctly.

WARNING: You can run multiple systems with different timesteps that all use the same PLUMED driver with i-Pi. The timestep that is passed from i-Pi to PLUMED is thus always one. The time column in any output file generated by PLUMED when it is running with i-Pi does not tell you how much time has elapsed since the start of the calculation.

WARNING: Masses and charges are not passed from i-pi to PLUMED. You thus cannot use features with this code that rely on masses and charges for the atoms being provided.  For example, you cannot use COM.

| Description of test | Status | 
|:--------------------|:------:| 
| MD code number of atoms passed correctly | [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](natoms_master.html) |
| MD code positions passed correctly | [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](positions_master.html) |
| MD code cell vectors passed correctly | [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](cell_master.html) |
| MD timestep passed correctly | [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](timestep_master.html) |
| PLUMED virial passed correctly | [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](virial_master.html) |
| MD code potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](energy_master.html) |
| PLUMED forces on potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](engforces_master.html) |
| PLUMED contribution to virial due to force on potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-failed-red.svg)](engvir_master.html) |