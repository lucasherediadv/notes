# Close laptop lid

Disabling Fedora doing anything closing laptop lid:

```
# /etc/systemd/logind.conf

HandleSuspendKey=ignore
HandleLidSwitch=ignore
HandleLidSwitchDocked=ignore
```

And then:

```
sudo systemctl restart systemd-logind
```

# Links

- [Reference](https://askubuntu.com/questions/15520/how-can-i-tell-ubuntu-to-do-nothing-when-i-close-my-laptop-lid)
