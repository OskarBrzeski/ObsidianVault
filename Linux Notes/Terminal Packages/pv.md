# How to Install
```bash
sudo pacman -S pv
```
# How to Use
```bash
command | pv > output
```
Progress Bar for Tar Archive
```bash
tar -cf - dir | pv -s $(du -sb dir | cut -f 1) > dir.tar
```

