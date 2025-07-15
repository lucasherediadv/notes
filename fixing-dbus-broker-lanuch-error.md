`Jun 25 13:27:50 localhost dbus-broker-launch[413]: Activation request for 'org.freedesktop.home1' failed: The systemd unit 'dbus-org.freedesktop.home1.service' could not be found.`

This can be fixed by preventing a specific file from begin extracted during `pacman` updates. In `/etc/pacman.conf` add this line:

`NoExtract = usr/lib/security/pam_systemd_home.so`

This changes stops `pacman` from installing the `pam_systemd_home.so` file, which causes the `dbus-broken-launch` error because the related `systemd` service isn't found.

[Related discussion](https://bbs.archlinux.org/viewtopic.php?pid=1927195#p1927195)
