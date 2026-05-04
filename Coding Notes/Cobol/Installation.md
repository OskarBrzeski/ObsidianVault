# Arch
```bash
sudo pacman -S gcc-gcobol
```

# Manual
Download from SourceForge: https://sourceforge.net/projects/gnucobol/files/

## Extract archive
Ensure you have `lzip` installed.
### Arch
```bash
sudo pacman -S lzip
```
### Debian
```bash
sudo nala install lzip
```

Extract the compressed tarball.
```bash
tar -xf gnucobol-3.2.tar.lz
cd gnucobol-3.2
```

## Dependencies
### Arch
```bash
sudo pacman -S make gcc gmp db
```
### Debian
```bash
sudo nala install libgmp-dev libdb5.3-dev
```
TODO: figure out shared object not found
## Install
Configure Makefile
```bash
./configure
```
Compile the compiler
```bash
make
```
Install the compiler
```bash
make install
```
# Usage
```bash
cobc
```
# Errors
## error while loading shared libraries: `libcob.so.4`
Ensure environment variable points to where the library can be found.
```bash
export LD_LIBRARY_PATH=/usr/local/lib:$LD_LIBRARY_PATH
```