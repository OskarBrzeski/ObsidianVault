`makepkg` is a Bash script which is used to create package archives that can be installed using [[pacman]].
## Installation
`makepkg` already exists in a standard Arch Linux install.

Ensure you have all of the needed dependencies using the following command:
```bash
sudo pacman -S git base-devel
```
## Usage
Make a package and install its dependencies:
```bash
makepkg -s
```

Make a package, install its dependencies and install it to the system:
```bash
makepkg -si
```

Generate `.SRCINFO` file for a repository:
```bash
makepkg --printsrcinfo > .SRCINFO
```
## Location
The `makepkg` script can be found in `/usr/bin/makepkg`.