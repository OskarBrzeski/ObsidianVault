# sudo fails to authenticate with correct password
One of these two was likely the solution.
```bash
faillock --reset

sudo -l
```

Also might be wise to do the following:
```bash
systemd start systemd-homed
```