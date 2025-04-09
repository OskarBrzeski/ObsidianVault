https://osu.ppy.sh/home

# How to install
## AppImage
```bash
curl --fail --remote-name --location --continue-at - {https://github.com/ppy/osu/releases/latest/download/osu.AppImage}
sudo chmod +x osu.AppImage
sudo mv -f osu.AppImage /usr/local/bin/osu
```
## Flatpak
```bash
flatpak install flathub sh.ppy.osu
```