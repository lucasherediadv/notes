# Avoid vimisms

Vimisms are the things Vim would have you do that damage your ability to
be productive on a system that has only Vi (not Vim). Learn the `vi`
compatible stuff first before using the rest.

Here is a list of some of them:

- `:r /tmp/foo` to read a file.
- `:n` next file.
- `Control-^` open previous file.
- `ZZ` instead of `:wq`, `:qw`, or `:x`.
- `:q!` instead of `ZQ`.
- `z.` instead of zz to center the screen.
- `G` always instead of `:`.
- `1G` instead of `gg`.
- Filters (`!!`, `!}`).
- Use `Control-[` instead of remapping `Esc`.
- Forget about `?` use `/` instead which wraps, then `N` to consistently
  go back.
- Forget about `e`.
- Forget about `R`.
- Do not use Vim visual mode, use filters and TMUX copy and paste
- Use TMUX panes instead of Vim splits.
