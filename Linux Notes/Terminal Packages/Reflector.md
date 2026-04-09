Script for fetching and ranking mirrors for pacman.
# Installation
## Arch
This script should
```bash
sudo pacman -S reflector
```
# Usage
```bash
sudo cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.backup
sudo reflector --country "United Kingdom" --protocol https --sort rate --save /etc/pacman.d/mirrorlist
```