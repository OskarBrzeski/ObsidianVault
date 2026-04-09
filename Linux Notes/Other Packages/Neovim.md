Text editor based on vim and using Lua for configuration.
https://neovim.io/
# Installation
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
# Config
Config files are stored in `~/.config/nvim`.

My current config can be found in https://github.com/OskarBrzeski/nvim-config
```bash
git clone https://github.com/OskarBrzeski/nvim-config ~/.config/nvim
```

To enable clipboard use, make sure you have a clipboard provider.
```bash
sudo pacman -S wl-clipboard  # Wayland (doesn't work currently)

sudo pacman -S xclip  # X11
```
