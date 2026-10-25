## Compiling quantum_espresso

To compile quantum_espresso and PLUMED the following bash script was used.
quantum_espresso was statically linked with the v" + stable_version + " of PLUMED.
In a separate build, the master version of PLUMED was linked to quantum_espresso as a runtime library.

Build with stable version download: [zipped raw stdout and stderr](stable_output.zip)

Build with master version download: [zipped raw stdout and stderr](master_output.zip)

```bash
# shellcheck disable=SC2154,2148
# Cloning the espresso repository
repo=https://gitlab.com/QEF/q-e.git
echo "cloning repoisitory $repo"
sourcedir=q-e$suffix
git clone https://gitlab.com/QEF/q-e.git "$sourcedir"

# Lets build quantum espresso
cd "$sourcedir" || {
  echo "cannot cd to $sourcedir" >&2
  # we want to build the site regardless
  exit 0
}
if [[ $mode = "static" ]]; then
  extraLIBS=LD_LIBS='-lmpi_cxx'
fi
# We build the interface with QE 7.0 because we are using the patch
git checkout qe-7.0
#shellcheck disable=SC2086
./configure --prefix="$HOME/opt" ${extraLIBS}
"plumed$suffix" patch --engine qespresso-7.0 -p --mode $mode
make pw
make install

```
