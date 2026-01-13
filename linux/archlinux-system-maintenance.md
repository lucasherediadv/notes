# Archlinux system maintenance

Regular system maintenance is crucial for ensuring the stability, performance, and security of archlinux over a period of time. These are the steps I follow periodically to keep my system in optimal conditions:

### Systemd

```
systemctl
systemctl --failed
systemctl status <unit>
systemd-analyze
systemd-analyze blame
systemctl list-units
systemctl list-unit-files
systemctl cat <service>
```

### Logging

```
journalctl
journalctl --boot
journalctl --boot --priority err
journalctl --lines 20 --no-pager --unit <service>
journalctl --dmesg
```

### Pacman

```
pacman -Qs <name>
pacman -Qtd
pacman -Qtd | pacman -Rns -
pacman -Qm
pacman -Qo <file>
pacman -Ql <package>
pacman -Sc
pacman -Qtd
```

```
paccache -r
paccache -ruk0
pacdiff --output
```

### Mirrors

```
reflector --latest 5 --protocol https --sort rate --save /etc/pacman.d/mirrorlist
```

### Clean the file system

```
lsblk --fs
ls -al ~/.cache ~/.config ~/.local/share
find / -type d \( -path "/dev" -o -path "/proc" -o -path "/run" -o -path "/sys" \) -prune -o -xtype l -print
```

### See also

[Arch Linux System Maintenance](https://wiki.archlinux.org/title/System_maintenance)
