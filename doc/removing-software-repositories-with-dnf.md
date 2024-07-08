# Removing softwares repositories with dnf

```
# Get a list of all configured repositories
dnf repolist

# Disable a repository
dnf config-manager --set-disabled <repo>
```

## Links

- [Source](https://docs.fedoraproject.org/en-US/quick-docs/adding-or-removing-software-repositories-in-fedora/)
