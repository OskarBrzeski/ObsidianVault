# COBOL front-end for GCC
## Arch
```bash
sudo pacman -S gcc-gcobol
```
# GnuCobol
## Debian
```bash
sudo nala install gnucobol
```
## Manual
Download from SourceForge: https://sourceforge.net/projects/gnucobol/files/
### **Extract archive**
Ensure you have `lzip` installed.

Arch
```bash
sudo pacman -S lzip
```
Debian
```bash
sudo nala install lzip
```

Extract the compressed tarball.
```bash
tar -xf gnucobol-3.2.tar.lz
cd gnucobol-3.2
```

### **Dependencies**
Arch
```bash
sudo pacman -S make gcc gmp db
```
Debian
```bash
sudo nala install make gcc libgmp-dev libdb-dev
```

### **Install**
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
sudo make install
```
