Compiling lammps
------------------------
 
To compile lammps and PLUMED the following bash script was used.  lammps was statically linked with the v2.9 of PLUMED. In a separate build, the master version of PLUMED was linked to lammps as a runtime library. 
 
Build with stable version download: [zipped raw stdout](stdout.txt.zip)  - [zipped raw stderr](stderr.txt.zip) 
 
Build with master version download: [zipped raw stdout](stdout_master.txt.zip)  - [zipped raw stderr](stderr_master.txt.zip) 

```bash
# Cloning the lammps repository
#repo=https://github.com/gtribello/lammps.git
repo=https://github.com/lammps/lammps.git
# https://github.com/lammps/lammps.git
echo "cloning repoisitory $repo"
git clone $repo lammps$suffix

# Finding the latest stable version of lammps to build
cd lammps$suffix
#version=$(git tag --sort=-creatordate | grep stable | head -n 1)
#version="fix-plumed-cmake"
echo "installing latest stable lammps $version"
#git checkout $version

# Building lammps using cmake
mkdir build
cd build
export PKG_CONFIG_PATH=$PKG_CONFIG_PATH:$HOME/opt/lib/pkgconfig
cmake -D CMAKE_CXX_COMPILER=mpic++ -D PKG_MANYBODY=yes -D PKG_KSPACE=yes -D PKG_MOLECULE=yes -D PKG_RIGID=yes -D PKG_PLUMED=yes -D PLUMED_MODE=$mode -D PLUMED_SUFFIX=$suffix ../cmake
make

if [ -f ./lmp ] ; then
   cp lmp $HOME/opt/bin/lammps
fi
```

