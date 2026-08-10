# Shell Keybind

`BASH` keybinds on Linux. Same as `Emacs` since they're both `GNU` programs.

## Reference

[Essential Keybindings For Bash, Fish and Zsh - DistroTube](https://www.youtube.com/watch?v=XY5qCQcrHns)

## Table of Contents

- [Navigation](#navigation)
- [Edit](#edit)
- [History](#history)
- [ETC](#etc)
- [VI Motions](#vi-motions)
  - [BASH](#bash)
  - [ZSH](#zsh)

---

## Navigation

- `ctrl + a`: beginning of the line
- `ctrl + e`: end of the line
- `ctrl + b`: move cursor backward
- `ctrl + f`: move cursor forward
- `alt + b`: move cursor backward by word
- `alt + f`: move cursor forward by word

> [!TIP]
> Try `command` instead of `alt` for **macOS**.

## Edit

- `ctrl + u`: delete from cursor to start of the line
- `ctrl + k`: delete from cursor to end of the line
- `ctrl + y`: undo
- `ctrl + w`: delete word backward
- `alt + d`: delete word forward

## History

- `ctrl + n`: same as arrow down
- `ctrl + p`: same as arrow up
- `!!`: use last command

## ETC

- `alt + period` / `!$`: use last argument
- `ctrl + l`: same as clear
- `ctrl + d`: same as exit

---

## VI Motions

Use `VI` motions instead of emacs

### BASH

In `~/.bashrc`:

```sh
set -e vi
bind 'set keyseq-timeout 1' # ESC delay to 1ms
```

Or in `~/.inputrc`:

```sh
set keyseq-timeout 1
```

### ZSH

In `~/.zshrc`:

```sh
bindkey -v
KEYTIMEOUT=1 # ESC delay to 10ms
```
