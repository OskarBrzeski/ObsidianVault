https://github.com/catppuccin/catppuccin
# How to install
## GNOME Terminal
```bash
curl -L https://raw.githubusercontent.com/catppuccin/gnome-terminal/v0.2.0/install.py | python3 -
```
Edit -> Preferences | Select Macchiato
## Btop
Download `themes.tar.gz` from https://github.com/catppuccin/btop/releases/tag/1.0.0
```bash
tar xf themes.tar.gz
cp themes/* $XDG_CONFIG_HOME/btop/themes
```
## Kitty
```bash
kitty +kitten themes --reload-in=all Catppuccin-Macchiato
```
