Ensure the `systemd-homed` service is active.

```bash
$ sudo systemctl enable --now systemd-homed
$ systemctl status systemd-homed
```

### Create the user

```bash
sudo homectl create username --storage=luks --member-of=wheel
```
