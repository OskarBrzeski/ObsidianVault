# Compiling
## Compile a program
```bash
gcc file.c  # results in a.out executable file
./a.out
```
## Compile a program with given name
```bash
gcc file.c -o outputname  # file extension can be ommitted
./outputname
```
## Include path for headers
```bash
gcc file.c -I./dirname/
```

# Libraries
## Compile a program with a library
```bash
gcc file.c -l{libname}
gcc file.c -lc -lm
```
## Compile a program with non-standard library
```bash
gcc file.c -L./libdir/ -lexample
gcc file.c -L./libdir/ -l:libexmpale.a
gcc file.c -L./libdir/ -l:libexample.so
```
