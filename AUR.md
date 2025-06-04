The Arch User Repository is a collection of git repositories that can be used to install packages on Arch Linux. Packages in the AUR are not present in the official Arch repositories and therefore cannot be installed using `pacman`.
## Prerequisites
To download AUR packages ensure you have `git` and `base-devel` installed:
```bash
sudo pacman -S git base-devel
```
This will ensure you have all of the necessary tools to create Arch packages.
## PKGBUILD
Packages in the AUR are installed using a `PKGBUILD` file, which is a Bash script. It contains information for the `makepkg` utility on how to build a package that can be installed onto Arch Linux using `pacman`.

A valid `PKGBUILD` file must have the following variables:
- `pkgname` - Name of the package
- `pkgver` - Version of the package
- `pkgrel` - Indicates changes when `pkgver` isn't changed
- `arch` - CPU architectures to be compiled for

Always review the `PKGBUILD` file before installing a package to ensure that it does not include malicious instructions, as almost all of them are made by the community.
## makepkg
`makepkg` is a utility that turns an AUR repository into a package archive.
## Install Package from AUR
Download the git repository of the package you wish to install:
```bash
git clone https://aur.archlinux.org/{package-name}.git
```
Enter the directory:
```bash
cd {package-name}
```
Review the `PKGBUILD` file:
```bash
vim PKGBUILD
```
Install the package:
```bash
makepkg -si
```
## .SRCINFO
This file contains metadata about the repository. Although it contains much of the same info as `PKGBUILD`, it does so in a format that is easier to parse and is used by the AUR web back-end to serve metadata.

To generate a `.SRCINFO` file, run the following command:
```bash
makepkg --printsrcinfo > .SRCINFO
```
## AUR helpers
AUR packages can be installed with ease using an AUR helper. The most commonly used helper is [[yay]].