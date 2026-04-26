# Compiling
## Compile a program
```bash
gcc file.c  # results in a.out executable file
./a.out
```
## Compile a program with given name
```bash
gcc -o outputname file.c  # file extension can be ommitted
./outputname  # run the compiled binary
```
## Compile an object file
```bash
gcc -c file.c  # results in a file.o object file
```
## Compile a program with object files
```bash
gcc -o outputname file.o
```
## Include path for headers
```bash
gcc file.c -I./dirname/
```
# Libraries
NOTE: Libraries must be included *after* the files, otherwise the linker decides to not work.
## Compile a program with a library
```bash
gcc file.c -l{libname}
gcc file.c -lc -lm
```
## Compile a program with non-standard library
```bash
gcc file.c -I./libdir/ -L./libdir/ -lexample
gcc file.c -I./libdir/ -L./libdir/ -l:libexmpale.a
gcc file.c -I./libdir/ -L./libdir/ -l:libexample.so
```

# Parallel compilation
## Compile with set number of cores
```bash
gcc -j4 ...
```
## Compile with all cores
```bash
gcc -j$(nproc) ...
```