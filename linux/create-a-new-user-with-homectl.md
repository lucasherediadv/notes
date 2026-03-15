Ensure the `systemd-homed` service is active.

```sh
$ sudo systemctl enable --now systemd-homed
$ systemctl status systemd-homed
```

Create the user

```sh
$ sudo homectl create username --storage=luks --member-of=wheel --umask=0077 --shell=/bin/bash
```
