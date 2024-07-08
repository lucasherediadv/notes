---
title: Ssh-copy-id
date: 2024-06-25
tags:
- Linux
---

`ssh-copy-id` install an SSH key on a server as an authorized key. Its purpose is to provide acces without requiring a password for each login.

This command edits the `authorized_keys` file on the server, creates the `~/.ssh` directory if it doesn't exists and creates the authorized keys file if it doesn't exist.
