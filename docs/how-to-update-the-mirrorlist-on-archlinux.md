# How to update the mirrorlist on archlinux

Get the fastest and most reliable mirrors for Arch Linux using
`reflector`.

`sudo reflector -l 200 -n 20 -p http,https --sort rate --save
/etc/pacman.d/mirrorlist`.

This command fetches the 200 most recently updated mirrors, sort them by
speed, filters out the top 20 that support either HTTP or HTTPS, and
saves them in the mirrorlist file.
