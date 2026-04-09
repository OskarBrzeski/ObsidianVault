Utility that provides a progress bar for some UNIX commands.
# Installation
```bash
sudo pacman -S pv
```
# Usage
```bash
command | pv > output
```
Progress Bar for Tar Archive
```bash
tar -cf - dir | pv -s $(du -sb dir | cut -f 1) > dir.tar
```

