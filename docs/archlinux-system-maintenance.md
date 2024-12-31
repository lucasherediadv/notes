# Arch Linux system maintenance

These are some of the commands I often use to keep a clean and up to date arch linux install.

## Systemd
```
systemctl status          # runtime info about the whole system
systemctl --type=service  # list all running services
systemctl --failed        # for failed units
systemd-analyze           # system boot-up performance statistics
systemd-analyze blame     # list of all running units ordered by the time they took to initialize
```

## Logging
```
journalctl                # print log entries from the systemd journal
journalctl -b 0 -p 4      # show "notice" messages and all higher priority log levels from the current boot
journalctl -k             # kernel messages, dmesg
```

## Pacman
```
pacman -Qen               # list packages explicitly installed
pacman -Qdtq              # list orphan packages
pacman -Qm                # list packages no longer in the remote repositories
pacman -Syu               # always use -Syu for upgrade
pacman -Sc                # remove cached packages that are not currently installed

# locating .pac* files
find /etc -name '*.pacnew' -o -name '*.pacsave'
grep '\.pacnew\|\.pacsave' /var/log/pacman.log
```
