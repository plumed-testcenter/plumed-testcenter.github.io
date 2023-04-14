Browse the tests
-----------------
The codes listed below below were tested on __April 14, 2023__. PLUMED-TESTCENTER tested whether the current and development versions of the code can be used to complete the tests for each of these codes.
 
| Name of Program  | Short description | Compiles | Passes tests | 
|:-----------------|:------------------|:--------:|:------------:| 
| [simplemd](https://www.plumed.org/doc-master/user-doc/html/simplemd.html) | A Lennard Jones molecular dynamics code that is part of PLUMED. |  [![tested on v2.9](https://img.shields.io/badge/v2.9-passing-green.svg)](tests/simplemd/install.html) [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](tests/simplemd/install.html) |  [![tested on v2.9](https://img.shields.io/badge/v2.9-partial-yellow.svg)](tests/simplemd/testout.html) [![tested on master](https://img.shields.io/badge/master-partial-yellow.svg)](tests/simplemd/testout_master.html) | 
| [lammps](https://www.lammps.org) | The Large-scale Atomic/Molecular Massively Parallel Simulator. An MD code that is often used for materials modelling. |  [![tested on v2.9](https://img.shields.io/badge/v2.9-failed-red.svg)](tests/lammps/install.html) [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](tests/lammps/install.html) |  [![tested on v2.9](https://img.shields.io/badge/v2.9-failed-red.svg)](tests/lammps/testout.html) [![tested on master](https://img.shields.io/badge/master-partial-yellow.svg)](tests/lammps/testout_master.html) | 
| [quantum_espresso](https://www.quantum-espresso.org) | An integrated suite of Open-Source computer codes for electronic-structure calculatiosn and materials modelling at the nanoscales that uses density-functional theory, plane waves and pseudopotentials. |  [![tested on v2.9](https://img.shields.io/badge/v2.9-passing-green.svg)](tests/quantum_espresso/install.html) [![tested on master](https://img.shields.io/badge/master-passing-green.svg)](tests/quantum_espresso/install.html) |  [![tested on v2.9](https://img.shields.io/badge/v2.9-partial-yellow.svg)](tests/quantum_espresso/testout.html) [![tested on master](https://img.shields.io/badge/master-partial-yellow.svg)](tests/quantum_espresso/testout_master.html) | 
 
**Building PLUMED**
 
When the tests above are run PLUMED is built using the following bash script.
 
```bash
#! /bin/bash

set -e
set -x

suffix=""
version=""
repo=https://github.com/plumed/plumed2.git
program_name=plumed

for opt
do
case "$opt" in
  (version=*) version="${opt#version=}" ;;
  (suffix=*)
     suffix="--program-suffix=${opt#suffix=}"
     program_name="plumed${opt#suffix=}"
   ;;
  (repo=*) repo="${opt#repo=}" ;;
  (*) echo "unknown option $opt" ; exit 1 ;;
esac
done

cd "$(mktemp -dt plumed.XXXXXX)"

git clone $repo
cd plumed2

if [ -n "$version" ] ; then
  echo "installing plumed $version"
else
  version=$(git tag --sort=-creatordate | grep '^v2\.[0-9][0-9]*\.[0-9][0-9]*' | head -n 1 )
  echo "installing latest stable plumed $version"
fi

git checkout $version

hash=$(git rev-parse HEAD)

if test -f $HOME/opt/lib/$program_name/$hash
then
  echo "ALREADY AVAILABLE, NO NEED TO REINSTALL"
else

rm -fr $HOME/opt/lib/$program_name
rm -fr $HOME/opt/bin/$program_name
rm -fr $HOME/opt/include/$program_name
rm -fr $HOME/opt/lib/lib$program_name.so*

./configure --prefix=$HOME/opt  --enable-modules=all --enable-boost_serialization --enable-fftw $suffix --enable-libtorch LDFLAGS=-Wl,-rpath,$LD_LIBRARY_PATH
make -j 5
make install

touch $HOME/opt/lib/$program_name/$hash

fi
```
