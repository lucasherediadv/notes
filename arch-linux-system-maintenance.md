Regular system maintenance is crucial for ensuring the stability, performance, and security of Arch Linux over a period of time. These are the steps I follow periodically to keep my system in optimal conditions:

### Systemd

```
systemctl list-units

# Lists if they are masked
systemctl list-unit-files

# Shows locations and contents of configuration files for <service>
systemctl cat <service>

# Check for any services that have failed to start or are in a failed state.
systemctl --failed

# Startup time. Append 'blame' for breakdown
systemd-analyze
```

### Logging

```
# Systemd has its own logging system called the journal.
journalctl

# Examine the journal for messages from the current boot.
journalctl --boot

# Filter the journal to display only error-level messages
journalctl --boot --priority err # 0, 1, 2, 3 ...

# Last lines for a specific unit
journalctl --lines 20 --no-pager --unit <service>

journalctl --since yesterday --until "1 hour ago"

# Kernel messages
journalctl --dmesg
```

```
# Additionally, manually inspect log files located in /var/log/ for any irregularities or error messages. 
```

### Pacman (Package Manager)

```
# Always use -Syu for updating the system
pacman -Syu

# Identify packages that were installed as dependencies
# but are no longer required by any explicitly installed package (Orphans).
pacman -Qtd

# Recursively remove orphans and their configuration files.
pacman -Qtd | pacman -Rns -

# List packages that are not from the official Arch Linux repositories.
pacman -Qm

```

```
# Package cache
# Remove all cached packages that are not currently installed on you system,
and clean up the unused sync databases
pacman -Sc

# Using paccache (from pacman-contrib package)
# Delete all cached versions of installed and uninstalled packages,
# keeping only the most recent three.
paccache -r
```

```
# Dealing with new configuration files.
# Locating .pac* files in the /etc directory using find.
find /etc -name '*.pacnew' -o -name '*.pacsave'

# Locating .pac* files using the pacman log.
grep '\.pacnew\|\.pacsave' /var/log/pacman.log

# Also you can use the pacdiff utility (part of the pacman-contrib package).
# It provides a side-by-side comparison, making it easier to integrate changes.
pacdiff

# Print files instead of merging them.
pacdiff --output
```

### Mirrors

```
# A well-sorted mirrorlist ensures faster and more reliable downloads during updates.

pacman -S reflector
reflector --latest 5 --sort rate --save /etc/pacman.d/mirrorlist
```

### Filesystem and volumes

```
fdisk --list
df --local --print-type
lsblk --fs
blkid /dev/sda
mount
cat /etc/fstab
```

```
# Over time, various applications can leave behind old configuration files, cached data,
# and temporary file, especially in the home directory.
# Common locations to check:
# - ~/.config/
# - ~/.cache/
# - ~/.local/share/
```

```
# Borken Symlinks
# Broek symbolic links point to file or directories thatt no longer exist.
# List broken symlinks, excluding common pseudo-filesystems (/dev, /proc, /run, /sys).
find / -type d \( -path "/dev" -o -path "/proc" -o -path "/run" -o -path "/sys" \) -prune -o -xtype l -print

# Carefully inspect the generated list. Only remove symlnks that your are certain are unnecessary or truly broken.
```
