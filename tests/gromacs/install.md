## Compiling gromacs

To compile gromacs and PLUMED the following bash script was used.
gromacs was statically linked with the v" + stable_version + " of PLUMED.
In a separate build, the master version of PLUMED was linked to gromacs as a runtime library.

Build with stable version download: [zipped raw stdout and stderr](stable_output.zip)

Build with master version download: [zipped raw stdout and stderr](master_output.zip)

```bash
# shellcheck disable=SC2154,2148
# Cloning the gromacs repository
# formatted with shfmt_v3.6.0
# Clone direclty into the wanted gromacs version
git clone --depth 1 --branch v2024.2 https://gitlab.com/gromacs/gromacs.git "gromacs$suffix"

cd "gromacs$suffix" || {
   echo "Something failed with cloning gromacs into gromacs$suffix" >&2
   # we want to build the site regardless
   exit 0
}

# Patch with PLUMED
"plumed$suffix" patch --engine gromacs-2024.2 -p --mode "$mode"

prefix=$HOME/opt/gromacs$suffix

# Run cmake
mkdir build
cd build || {
   echo "cannot cd to build" >&2
   # we want to build the site regardless
   exit 0
}
# Adding GMX_MPI so the statically linked version will link correcly to mpi things
# -Wno-dev because we don't care about dev warnings here
cmake .. -DGMX_BUILD_OWN_FFTW=ON -DCMAKE_INSTALL_PREFIX="$prefix" -DGMX_ENABLE_CCACHE=ON -Wno-dev -DGMX_MPI=ON

cmake --build . -j4
cmake --install .

if [ -x "${prefix}/bin/gmx_mpi" ]; then
   # Write a script to execute gromacs calculations
   executible=$HOME/opt/bin/gromacs$exeSuffix
   cat <<EOF >"$executible"
#!/bin/bash
export PLUMED_KERNEL=$plumedKernel
mygmx=$prefix/bin/gmx_mpi
"\$mygmx" grompp -p topol.top -c conf.gro -f md.mdp
"\$mygmx" mdrun -plumed plumed.dat
echo 5 | "\$mygmx" energy
EOF
   chmod u+x "$executible"
else
   echo "${prefix}/bin/gmx_mpi" have not been compiled or is not executable
fi

```
