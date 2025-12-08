https://qertoip.medium.com/how-to-fix-dns-issues-when-using-mullvad-wireguard-networkmanager-on-linux-55fc14453a91
```bash
sudo pacman -Rs systemd-resolvconf
sudo pacman -Rs openresolv
sudo pacman -Rs bind
sudo pacman -Rs unbound

sudo ln -sf /run/systemd/resolve/stub-resolv.conf /etc/resolv.conf
sudo systemctl enable systemd-resolved
sudo systemctl start systemd-resolved

sudo systemctl stop mullvad-daemon
sudo systemctl restart systemd-resolved
sudo systemctl restart NetworkManager
sudo ststemctl enable mullvad-daemon
sudo systemctl start mullvad-daemon
```