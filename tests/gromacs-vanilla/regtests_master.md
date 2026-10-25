Regression tests of gromacs-vanilla with PLUMED master
------------------------

These tests are specific to gromacs-vanilla: they check parts of its interface with PLUMED that the general tests do not cover.
Each test checks a property that must hold for any version of PLUMED and of gromacs-vanilla, such as a PLUMED bias that must act as
the same bias applied by gromacs-vanilla, or the same simulation that must give the same results in two ways of running it, so that
no reference results are stored.
A test is skipped when this version of gromacs-vanilla does not have the feature it tests.
The tests, and how to run them on your own computer, are in the
[directory of the code](https://github.com/plumed-testcenter/plumed-testcenter/tree/main/tests/gromacs-vanilla) in the repository of
the testcenter.

| Test | What it checks | Status | Result |
|:-----|:---------------|:------:|:-------|
| energy | ENERGY equals the potential energy of GROMACS at every step, on 1 and 2 ranks | ![FAIL](https://img.shields.io/badge/master-failed-red.svg) | 1 ranks: ENERGY differs from the potential energy by 1 (relative) |
| pull | a RESTRAINT on the distance of two water oxygens acts as the GROMACS pull code: same positions over 20 steps, forces at step 0, and virial every 5 steps (the virial is computed on those steps only) | ![PASS](https://img.shields.io/badge/master-passed-green.svg) | PLUMED against pull code, 1 rank: max \|dx\| 0 nm, \|df\|/max\|f\| at step 0 0, \|dvirial\| at step 0 0 kJ/mol, max 0.00195 kJ/mol |
| pull-dd | as pull, on 2 ranks | ![PASS](https://img.shields.io/badge/master-passed-green.svg) | PLUMED against pull code, 2 ranks: max \|dx\| 1e-05 nm, \|df\|/max\|f\| at step 0 7.4e-09, \|dvirial\| at step 0 0 kJ/mol, max 0.113 kJ/mol |
| pull-energy | as pull, with ENERGY in the PLUMED input (PLUMED then runs when the energy is complete) | ![PASS](https://img.shields.io/badge/master-passed-green.svg) | PLUMED against pull code, 1 rank: max \|dx\| 0 nm, \|df\|/max\|f\| at step 0 0, \|dvirial\| at step 0 0 kJ/mol, max 0.00195 kJ/mol |
| pull-mts | as pull, with multiple time stepping and ENERGY needed on the slow steps | ![PASS](https://img.shields.io/badge/master-passed-green.svg) | PLUMED against pull code, 1 rank: max \|dx\| 1e-05 nm, \|df\|/max\|f\| at step 0 0, \|dvirial\| at step 0 0 kJ/mol, max 0.082 kJ/mol |
| mts-fast-step | with multiple time stepping, mdrun stops with an error if PLUMED needs the energy on a fast step | ![FAIL](https://img.shields.io/badge/master-failed-red.svg) | mdrun exit 0, with no error about MTS |
| vsite | a RESTRAINT between two virtual sites (TIP4P M sites) acts the same with and without ENERGY in the PLUMED input (with ENERGY, PLUMED runs after GROMACS spread the forces on the virtual sites), on 1 and 2 ranks | ![PASS](https://img.shields.io/badge/master-passed-green.svg) | with ENERGY against without, 1 rank: max \|dx\| 0 nm, \|df\|/max\|f\| at step 0 0, \|dvirial\| at step 0 0 kJ/mol, max 0 kJ/mol; with ENERGY against without, 2 ranks: max \|dx\| 1e-05 nm, \|df\|/max\|f\| at step 0 7.4e-09, \|dvirial\| at step 0 0.0039 kJ/mol, max 0.166 kJ/mol |
| energy-bias | a bias s\*ENERGY multiplies all the forces by 1+s, also with virtual sites | ![FAIL](https://img.shields.io/badge/master-failed-red.svg) | forces differ from 0.5 times the unbiased ones by up to 0.999 of the largest force |
| energy-bias-dd | with a bias on ENERGY, the virial is the same on 1, 2 and 3 ranks | ![PASS](https://img.shields.io/badge/master-passed-green.svg) | same virial within 0.00031 kJ/mol |
| em | energy minimization with a restraint: the same steps on 1 and 2 ranks, and with and without ENERGY (restraints between two oxygens and between two virtual sites) | ![PASS](https://img.shields.io/badge/master-passed-green.svg) | oxygens: same 18 distances; vsites: same 19 distances |
| data | PLUMED gets the positions, box, masses, charges and time of GROMACS | ![PASS](https://img.shields.io/badge/master-passed-green.svg) | positions, box, time, masses and charges match |
| checkpoint | PLUMED writes its state (OPES STATE\_WFILE with STORE\_STATES) at the steps where GROMACS writes a checkpoint, on 1 and 2 ranks | ![FAIL](https://img.shields.io/badge/master-failed-red.svg) | 1 ranks: states at steps \[3125, 5175, 7325, 9450, 11550, 13675, 15800, 17925, 20000\], checkpoints at \[2175, 4225, 6375, 8500, 10600, 12725, 14850, 16975, 19050, 20000\] |
| committor | COMMITTOR stops mdrun soon after committing, with a final checkpoint, on 1 and 2 ranks | ![FAIL](https://img.shields.io/badge/master-failed-red.svg) | 1 ranks: committed at step 250, ran to step 20000 |
| committor-walkers | with two simulations (-multidir), all of them stop when one commits | ![FAIL](https://img.shields.io/badge/master-failed-red.svg) | last steps \[20000, 20000\] |
| rerun | a rerun of a trajectory gives the CVs that PLUMED computed in the run, on 1 and 2 ranks; a stop request (COMMITTOR) ends the rerun | ![FAIL](https://img.shields.io/badge/master-failed-red.svg) | rerun with COMMITTOR: committed at time 0.04, stopped after 11 of 11 frames (last time 0.4) |
| hrex | -hrex with two identical replicas: the PLUMED energy difference is 0 (1 and 2 ranks per replica), and PLUMED does not calculate again on the exchange steps (one COLVAR line per step, the expected hills) | ![SKIP](https://img.shields.io/badge/master-skipped-lightgrey.svg) | -hrex is only in the legacy patches |
| shells | shell (polarizable) particles: PLUMED is applied once per step, also in a rerun, and mdrun warns when PLUMED needs the energy, which is the one before the shells are relaxed (or mdrun refuses shells) | ![FAIL](https://img.shields.io/badge/master-failed-red.svg) | 44 COLVAR lines (21 distinct), 6 hills |
| expanded | expanded ensemble: PLUMED's lambda is the lambda state of GROMACS; with lmc-stats other than 'no', GROMACS still updates the weights | ![SKIP](https://img.shields.io/badge/master-skipped-lightgrey.svg) | lambda dynamics with PLUMED is only in the legacy patches |
| md-vv | md-vv runs with PLUMED (the legacy patches use the legacy simulator, which supports it) | ![PASS](https://img.shields.io/badge/master-passed-green.svg) | runs |
| replex-nex | replica exchange with -nex, which ignores the PLUMED bias, is refused | ![SKIP](https://img.shields.io/badge/master-skipped-lightgrey.svg) | replica exchange with a PLUMED bias is only in the legacy patches |
| replex-bias | temperature replica exchange with a PLUMED bias: the legacy patches add the bias to the exchange criterion; the native module refuses it with a clear error | ![FAIL](https://img.shields.io/badge/master-failed-red.svg) | mdrun ran replica exchange without the PLUMED bias in the exchange criterion, and without an error |
| gpu-buffer-ops | with nonbonded and PME on the GPU, the restraint acts the same with GPU force buffer operations | ![SKIP](https://img.shields.io/badge/master-skipped-lightgrey.svg) | not a CUDA build |


The text files of the runs (inputs, logs and output of PLUMED) are available in this [zip archive](regtests_master.zip).
