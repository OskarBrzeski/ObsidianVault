# How to use
Install a package
```bash
pacman -S <package-name>
pacman -S extra/<package-name>  # from specific repository
pacman -S <partial-name>-{pkg1,pkg2}
```
Check what packages belong to a group
```bash
pacman -Sg <package-group>
```
Update packages
```bash
pacman -Syu
```
Remove a package
```bash
pacman -R <package-name>
pacman -Rs <package-name>  # also removes dependencies
```
Remove a package group
```bash
pacman -Rsu <package-group>
```
List orphaned packages
```bash
pacman -Qdt
```
Remove orphaned packages
```bash
pacman -Qdtq | pacman -Rns -
```