Virtual Machine.
https://computingforgeeks.com/install-kvm-qemu-virt-manager-arch-manjar/
https://wiki.archlinux.org/title/QEMU
# Installation
## Check if virtualisation is on
```bash
grep -E -c '(vmx|svm)' /proc/cpuinfo
```
## Install packages
```bash
sudo pacman -S qemu[-full|-desktop] virt-manager virt-viewer dnsmasq vde2 bridge-utils openbsd-netcat dmidecode ebtables iptables libguestfs
```
## Enable services
```bash
sudo systemctl enable libvirtd.service
sudo systemctl start libvirtd.service
# check service status
sudo systemctl status libvirtd.service
```
## Edit config file
```bash
sudo nvim /etc/libvirt/libvirtd.conf
```

```
# Line 85
unix_sock_group = "libvirt"
# Line 108
unix_sock_rw_perms = "0770"
```
## Set up user group
```bash
sudo usermod -aG libvirt $USER
sudo usermod -aG libvirt-qemu $USER
sudo usermod -aG kvm $USER
sudo usermod -aG input $USER
sudo usermod -aG disk $USER
newgrp libvirt  # might be unneeded
sudo systemctl restart libvirtd.service
```
## Auto-start network
```bash
sudo virsh net-start default
sudo virsh net-autostart default
sudo virsh net-list --all
```

Once done, reboot and start using Virtual Machine Manager.
# Troubleshooting
## Unable to open /dev/net/tun, is tun module loaded?
Running kernel is different from installed kernel. Reboot system to fix.

Virt Manager should work as long as these two commands give the same output.
```bash
pacman -Q linux
uname -r
```