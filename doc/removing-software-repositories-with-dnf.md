# Removing softwares repositories with dnf

Get a list of all configured repositories.

```
dnf repolist
```

To disable a particular repository, run the following command.

```
dnf config-manager --set-disabled <repo>
```

Finally get a list of disabled repositories.

```
dnf repolist disabled
```

## Links

- [Source](https://docs.fedoraproject.org/en-US/quick-docs/adding-or-removing-software-repositories-in-fedora/)
