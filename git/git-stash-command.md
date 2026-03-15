`git stash` is a way to save your local changes without committing them. It's like making a save point.

```sh
# Save the state of your local changes in a stash
git stash

# Only stash the given file
git stash push ./stash.md

# Restore the local changes from the stash, and remove it from the stash list
git stash pop

# Same as 'pop', but doesn't remove the stash from the list
git stash apply

# A message that will show up in 'git stash list'
git stash -m "This is a stash message"

# List all stashes in the stash list
git stash list

# Pop the stash with the given index
git stash pop stash@{1}

# Show the truncated diff for the stash at the top of the stash list
git stash show

# Show the full diff for the stash at the top of the stash list
git stash show -p

# Remove all the stash entries
git stash clear
```
