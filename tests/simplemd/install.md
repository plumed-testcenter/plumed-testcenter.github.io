## Compiling simplemd

To compile simplemd and PLUMED the following bash script was used.
simplemd was statically linked with the v" + stable_version + " of PLUMED.
In a separate build, the master version of PLUMED was linked to simplemd as a runtime library.

Build with stable version download: [zipped raw stdout and stderr](stable_output.zip)

Build with master version download: [zipped raw stdout and stderr](master_output.zip)

```bash
# Some dummy code as we don't need to do anything to build simplemd 
# if plumed has been built
echo Hello simplemd world

```
