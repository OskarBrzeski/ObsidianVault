# Nuphy.io: Unable to get device authorization
https://www.reddit.com/r/NuPhy/comments/1hnn89w/unable_to_get_device_authorization_for_air60he/
```bash
sudoedit /etc/udev/rules.d/99-hidraw.rules
```
Inside above file:
```
KERNEL=="hidraw*", SUBSYSTEM=="hidraw", GROUP="hidraw", MODE="0660"
```

```bash
sudo udevadm control --reload-rules
sudo udevadm trigger
sudo groupadd -r hidraw
sudo usermod -a -G hidraw $USER
```