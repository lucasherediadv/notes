Install the `docker` package and `docker-buildx` to use the current builder instead of the deprecated legacy builder.

```sh
$ sudo pacman -S docker docker-buildx
```

Next enable/start the `docker.service` or `docker.socket`. Note that `docker.service` starts the service on boot, whereas `docker.socket` starts `docker` on first usage which can decrease boot times.

Then verify docker's status:

```sh
$ docker info
```

If you want to be able to run `docker` CLI commands as non-root user, add your user to the `docker` user group, re-login and restart `docker.service`
