Man pages can be searched when the exact name of a page is not known using any of the following equivalent commands:

```console
$ man -k expression
$ man --apropos expression
$ apropos expression
```

To search for keywords in whole page texts, use the `-K` option instead.

If you are getting "nothing appropriate" message for every search, try manually regenerating the cache by running `mandb` as root.

One-line descriptions of man pages can be displayed using the `whatis` command:

```console
$ whatis ls
```
