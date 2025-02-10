https://neovim.io/
# How to install
## Arch
```bash
sudo pacman -S neovim
```
## AppImage
```bash
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim.appimage
sudo chmod +x nvim.appimage
sudo mv nvim.appimage /usr/local/bin/nvim
```
# How to use
```bash
nvim [file-name]
```
## Config
Config files are stored in `~/.config/nvim`.

To enable clipboard use, make sure you have a clipboard provider.
```bash
sudo pacman -S wl-clipboard  # Wayland
```
