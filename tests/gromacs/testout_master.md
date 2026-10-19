Testing gromacs
------------------------
 
The tests described in the following tables were performed on __October 19, 2026__ to test whether the interface between gromacs and the master version of PLUMED is working correctly.

## Basic functionalities

| Description of test | Status | 
|:--------------------|:------:| 
| MD code number of atoms passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](natoms_master.html) |
| MD code positions passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](positions_master.html) |
| MD code cell vectors passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](cell_master.html) |
| MD timestep passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](timestep_master.html) |
| MD code masses passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](mass_master.html) |
| MD code charges passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](charge_master.html) |

## Tests on virial

| Description of test | Status | 
|:--------------------|:------:| 
| PLUMED virial passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](virial_master.html) |


## Tests on energy

| Description of test | Status | 
|:--------------------|:------:| 
| MD code potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](energy_master.html) |
| PLUMED forces on potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](engforces_master.html) |
| PLUMED contribution to virial due to force on potential energy passed correctly | [![tested on master](https://img.shields.io/badge/master-fail%200%25-green.svg)](engvir_master.html) |


## Regression tests

Tests specific to gromacs: the results and the numbers are in [this report](regtests_master.html).

| Description of test | Status | 
|:--------------------|:------:| 
| energy: ENERGY equals the potential energy of GROMACS at every step, on 1 and 2 ranks | [![energy on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| pull: a RESTRAINT on the distance of two water oxygens acts as the GROMACS pull code: same positions over 20 steps, forces at step 0, and virial every 5 steps (the virial is computed on those steps only) | [![pull on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| pull-dd: as pull, on 2 ranks | [![pull-dd on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| pull-energy: as pull, with ENERGY in the PLUMED input (PLUMED then runs when the energy is complete) | [![pull-energy on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| pull-mts: as pull, with multiple time stepping and ENERGY needed on the slow steps | [![pull-mts on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| mts-fast-step: with multiple time stepping, mdrun stops with an error if PLUMED needs the energy on a fast step | [![mts-fast-step on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| vsite: a RESTRAINT between two virtual sites (TIP4P M sites) acts the same with and without ENERGY in the PLUMED input (with ENERGY, PLUMED runs after GROMACS spread the forces on the virtual sites), on 1 and 2 ranks | [![vsite on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| energy-bias: a bias s\*ENERGY multiplies all the forces by 1+s, also with virtual sites | [![energy-bias on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| energy-bias-dd: with a bias on ENERGY, the virial is the same on 1, 2 and 3 ranks | [![energy-bias-dd on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| em: energy minimization with a restraint: the same steps on 1 and 2 ranks, and with and without ENERGY (restraints between two oxygens and between two virtual sites) | [![em on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| data: PLUMED gets the positions, box, masses, charges and time of GROMACS | [![data on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| checkpoint: PLUMED writes its state (OPES STATE\_WFILE with STORE\_STATES) at the steps where GROMACS writes a checkpoint, on 1 and 2 ranks | [![checkpoint on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| committor: COMMITTOR stops mdrun soon after committing, with a final checkpoint, on 1 and 2 ranks | [![committor on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| committor-walkers: with two simulations (-multidir), all of them stop when one commits | [![committor-walkers on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| rerun: a rerun of a trajectory gives the CVs that PLUMED computed in the run, on 1 and 2 ranks; a stop request (COMMITTOR) ends the rerun | [![rerun on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| hrex: -hrex with two identical replicas: the PLUMED energy difference is 0 (1 and 2 ranks per replica), and PLUMED does not calculate again on the exchange steps (one COLVAR line per step, the expected hills) | [![hrex on master](https://img.shields.io/badge/master-skipped-lightgrey.svg)](regtests_master.html) |
| shells: shell (polarizable) particles: PLUMED is applied once per step, also in a rerun, and mdrun warns when PLUMED needs the energy, which is the one before the shells are relaxed (or mdrun refuses shells) | [![shells on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| expanded: expanded ensemble: PLUMED's lambda is the lambda state of GROMACS; with lmc-stats other than 'no', GROMACS still updates the weights | [![expanded on master](https://img.shields.io/badge/master-skipped-lightgrey.svg)](regtests_master.html) |
| md-vv: md-vv runs with PLUMED (the legacy patches use the legacy simulator, which supports it) | [![md-vv on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| replex-nex: replica exchange with -nex, which ignores the PLUMED bias, is refused | [![replex-nex on master](https://img.shields.io/badge/master-skipped-lightgrey.svg)](regtests_master.html) |
| replex-bias: temperature replica exchange with a PLUMED bias: the legacy patches add the bias to the exchange criterion; the native module refuses it with a clear error | [![replex-bias on master](https://img.shields.io/badge/master-passed-green.svg)](regtests_master.html) |
| gpu-buffer-ops: with nonbonded and PME on the GPU, the restraint acts the same with GPU force buffer operations | [![gpu-buffer-ops on master](https://img.shields.io/badge/master-skipped-lightgrey.svg)](regtests_master.html) |
