# Terminal
Compile COBOL code.
```bash
gcobol file.cob
gcobol file.cob -o executable
```
# Errors
## error while loading shared libraries: `libcob.so.4`
Ensure environment variable points to where the library can be found.
```bash
export LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH
```