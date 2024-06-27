Compiling quantum_espresso
------------------------
 
To compile quantum_espresso and PLUMED the following bash script was used.  quantum_espresso was statically linked with the v2.9 of PLUMED. In a separate build, the master version of PLUMED was linked to quantum_espresso as a runtime library. 
 
Build with stable version download: [zipped raw stdout](stdout.txt.zip)  - [zipped raw stderr](stderr.txt.zip) 
 
Build with master version download: [zipped raw stdout](stdout_master.txt.zip)  - [zipped raw stderr](stderr_master.txt.zip) 

```bash
# Cloning the espresso repository
repo=https://gitlab.com/QEF/q-e.git
echo "cloning repoisitory $repo"
git clone https://gitlab.com/QEF/q-e.git q-e$suffix

# Lets build quantum espresso
cd q-e$suffix
if [[ $mode = "static" ]]; then
  extraLIBS="LD_LIBS='-lmpi_cxx'"
fi
# We build the interface with QE 7.0 because we are using the patch
git checkout qe-7.0
./configure --prefix="$HOME/opt" $extraLIBS
plumed$suffix patch --engine qespresso-7.0 -p --mode $mode
make pw
make install
```

