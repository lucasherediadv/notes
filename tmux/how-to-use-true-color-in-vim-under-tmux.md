`.tmux.conf`:

```
set -g default-terminal "tmux-256color"
set -ga terminal-overrides ",*256col*:Tc"
```

`.vimrc`:

```
if exists('+termguicolors')
  set termguicolors
endif
```
