https://wiki.archlinux.org/title/CUPS
# Enable CUPS
```bash
sudo systemctl enable cups
sudo systemctl start cups
```
# Enable Avahi
```bash
sudo systemctl enable avahi-daemon
sudo systemctl start avahi-daemon
```
# Discover Printer on local network
```bash
lpadmin -p PrinterName -E -v "ipp:/i92.168.x.x/ipp/print" -m everywhere
```