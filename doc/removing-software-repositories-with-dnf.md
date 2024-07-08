---
title: Removing repositories with dnf
date: 2024-06-27
tags:
- Linux
---

```
# Get a list of all configured repositories
dnf repolist

# Disable a repository
dnf config-manager --set-disabled <repo>
```
