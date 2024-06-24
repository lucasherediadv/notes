# Bootable usb from cli

```
# Download image
wget https://download.fedoraproject.org/pub/fedora/linux/releases/40/Server/x86_64/iso/Fedora-Server-dvd-x86_64-40-1.14.iso

# Retrieve a list of attached devices
lsblk

# Umount the device
sudo umount /dev/[device]

# Transfer the downloaded image to the usb device
dd if=/path/to/Fedora-Server-dvd-x86_64-40-1.14.iso of=/dev/[device] bs=8M status=progress
```

Insert the bootable USB into the target device and reboot.

## Links

- [Create a bootable installation medium](https://docs.fedoraproject.org/en-US/fedora-server/installation/#_create_a_bootable_installation_medium)
