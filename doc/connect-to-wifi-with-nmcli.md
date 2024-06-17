# Connect to wifi with nmcli

Fortunately Fedora supports my wifi card, so my next problem is connecting to a wifi network.

See the status of all networks interfaces:
```
nmcli dev status
```

List available networks:
```
nmcli dev wifi list
```

Connect to a network:
```
nmcli dev wifi connect "network_ssid" password "password"
```

Network manager will save the connection and auto connect on reboot.

# Links

- []()
