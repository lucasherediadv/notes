```
lsblk
umount /dev/sdX
dd bs=4M if=/path/to/image.iso of=/dev/sdX status=progress oflag=sync
sync
```
