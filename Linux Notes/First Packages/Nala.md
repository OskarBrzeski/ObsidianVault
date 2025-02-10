https://phoenixnap.com/kb/nala-apt
# How to install
```bash
sudo apt upgrade && sudo apt update
sudo apt install nala
```
# How to use
Installing a package
```bash
sudo nala install [package-name]
```
Removing a package
```bash
sudo nala remove [package-name]
```
Removing a package and related config files
```bash
sudo nala purge [package-name]
```
Update packages
```bash
sudo nala update
```
Upgrade packages
```bash
sudo nala upgrade
```
List packages
```bash
nala list
nala list [regex]
```
List installed packages
```bash
nala list --installed
nala list -i

nala list --nala-installed
nala list -N
```
List upgradeable packages
```bash
nala list --upgradeable
```
Show history
```bash
nala history
```
