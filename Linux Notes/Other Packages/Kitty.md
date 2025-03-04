https://sw.kovidgoyal.net/kitty/
# How to install
## Arch
```bash
sudo pacman -S kitty
```
## Terminal
```bash
curl -L https://sw.kovidgoyal.net/kitty/installer.sh | sh /dev/stdin
ln -sf ~/.local/kitty.app/bin/kitty ~/.local/kitty.app/bin/kitten ~/.local/bin/

# Place the kitty.desktop file somewhere it can be found by the OS
cp ~/.local/kitty.app/share/applications/kitty.desktop ~/.local/share/applications/
# If you want to open text files and images in kitty via your file manager also add the kitty-open.desktop file
cp ~/.local/kitty.app/share/applications/kitty-open.desktop ~/.local/share/applications/
# Update the paths to the kitty and its icon in the kitty.desktop file(s)
sed -i "s|Icon=kitty|Icon=/home/$USER/.local/kitty.app/share/icons/hicolor/256x256/apps/kitty.png|g" ~/.local/share/applications/kitty*.desktop
sed -i "s|Exec=kitty|Exec=/home/$USER/.local/kitty.app/bin/kitty|g" ~/.local/share/applications/kitty*.desktop
```
# How to update
```bash
curl -L https://sw.kovidgoyal.net/kitty/installer.sh | sh /dev/stdin
```
# How to Use
The Kitty modifier key is `Ctrl+Shift`. I will henceforth refer to this as `KittyMod`.
Create new tab
```
KittyMod t
```
Move between tabs
```
KittyMod Left-Arrow   # previous tab
KittyMod Right-Arrow  # next tab
```
Create new window (pane)
```
KittyMod Enter
```
Move between windows
```
KittyMod [  # previous window
KittyMod ]  # next window
```
# Config
The config file can be found in `~/.config/kitty/kitty.conf`.