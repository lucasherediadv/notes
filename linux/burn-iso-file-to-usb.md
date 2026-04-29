The drive must not be in use while writing the image:
`umount /dev/sdX`

Write the ISO file with `dd`:
`sudo dd bs=4M if=/path/to/image.iso of=/dev/sdX status=progress oflag=sync`

Ensure the cache is cleared:
`sync`
