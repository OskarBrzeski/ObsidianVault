When using Arch Linux, it is possible to add the optimised CachyOS repositories as sources to download packages from.
# Installation
```bash
curl https://mirror.cachyos.org/cachyos-repo.tar.xz -o cachyos-repo.tar.xz
tar xvf cachyos-repo.tar.xz && cd cachyos-repo
sudo ./cachyos-repo.sh
```

This will add the CachyOS repos to `/etc/pacman.conf` and all necessary mirrorlists to `/etc/pacman.d/`.