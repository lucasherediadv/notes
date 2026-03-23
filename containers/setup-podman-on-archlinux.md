Install the `podman` package. If you want to replace `docker`, one can install `podman-docker` to mimic the `docker` binary along with man pages.

## Rootless `podman`

### Enable `kernel.unprivileged_userns_clone`

Check the value of `kernel.unprivileged_userns_clone` by running:

```bash
$ sysctl kernel.unprivileged_userns_clone
```

If it is currently set to `0`, enable it by setting `1` via `sysctl` or a kernel parameter.

### Set `subuid` and `subgid`

In order for users to run rootless `podman`, a `subuid` and `subgid` configuration entry must exist for each user that wants to use it. New users created using `useradd` have these entries by default.

## Runtime

* `runc`: The former default runtime.
* `crun`: The new default runtime. Generally preferable since is faster than `runc`.
