---
title: Manage wifi connections from cli
date: 2024-07-08
tags:
- linux
- nmcli
- networking
---

Manage wifi connections with the `nmcli` command.

```
# See the status of all network interfaces
nmcli dev status

# List available networks
nmcli dev wifi list

# Connect to a network
nmcli dev wifi connect "SSID" password "password"

# Disconnect
nmcli connection down "SSID"
```
