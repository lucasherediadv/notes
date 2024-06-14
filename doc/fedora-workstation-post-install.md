# Fedora workstation installation

- Set up drive encryption
- Use ZRAM instead of Swap (Fedora uses ZRAM by default)
- System update: `sudo dnf upgrade`
- Update firmware:
```
sudo fwupdmgr get-devices
sudo fwupdmgr get-updates
sudo fwupdmgr update
```
- Randomize MAC address:
```
# /etc/NetworkManager/conf.d/00-random-mac-addresses.conf

[device]
wifi.scan-rand-mac-address=yes

[connection]
wifi.cloned-mac-address=random
ethernet.cloned-mac-address=random
connection.stable-id=${CONNECTION}/${BOOT}
```
- Hostnames: hostname
- Usernames: user
- Machine ID
```
# /etc/machine-id

# Generic machine ID
b08dfa6083e7567a1921a715000001fb
```
- System Counting:
```
# /etc/dnf/dnf.conf

countme=false
```

# Links

- [Linux General Recomendations](https://www.privacyguides.org/en/os/linux-overview/#general-recommendations)
