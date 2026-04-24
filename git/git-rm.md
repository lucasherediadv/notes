```
git rm -r --cached ./path/to/file/or/directory
```

Useful when you have accidentally committed files that should have been ignored. Think of it as a "reset tracking" command. It does not delete your physical files; it just tells `git` to "forget" them.

`--cached`: This is the most important flag. It specifies that the file should be removed only from the `git` index (the staging area/history) and not from your local hard drive.
