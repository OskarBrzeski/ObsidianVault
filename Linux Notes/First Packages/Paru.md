# Installation
## CachyOS repositories
```bash
sudo pacman -S paru
```
## Manual Installation
```bash
sudo pacman -S --needed base-devel
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
```
# Usage
Paru commands are almost identical to those of [[Pacman]], with a few key differences.
## Remove installed package
```bash
paru -Rns package-name
```
## Show statistics for installed packages
```bash
paru -Ps
```
# Notes
Paru will automatically show you the PKGBUILD file for the AUR package you wish to install. It is recommended to read through this file to ensure that it won't do anything suspicious.