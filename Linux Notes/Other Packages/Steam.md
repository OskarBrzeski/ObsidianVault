https://store.steampowered.com
# How to install
## Arch
```bash
sudo pacman -S steam
```
## Debian
```bash
sudo nala install steam
```
# Troubleshooting
# Game crashes on launch
Try using the following flag in the start up options:
```
PROTON_USE_WINED3D=1 %command%
```