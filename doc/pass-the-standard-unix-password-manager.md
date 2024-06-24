# Pass the standard unix password manager

Pass is a simple command line tool to manage passwords. Here are the steps I took to configure it.

```
# Generate a GPG keypair
gpg --full-generate-key

# Initiate pass with the GPG key ID
pass init  "GPGKEYID"

# Initiate Git repository
pass git init
```

At the moment I will not use a remote repository to backup passwords.

## Links

- [Pass](https://www.passwordstore.org/)
- [Pass Data Organization](pass-data-organization.md)
