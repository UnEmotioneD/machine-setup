# Vim

I use [Vim](https://www.vim.org/) by the way.

## Table of Contents

- [Vim Plug](#vim-plug)
- [Motions](#motions)
  - [Substitute](#substitute)
  - [Global](#global)
  - [Refactoring](#refactoring)

---

## Vim Plug

Built-in plugin manager.

### Install

Install vim-plug at `~/.vim/autoload/plug.vim`:

```sh
curl -fLo \
  ~/.vim/autoload/plug.vim --create-dirs \
  https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

### Usage

Add it to `~/.vimrc`:

```vim
call plug#begin('~/.vim/plugged')

" for example
Plug 'christoomey/vim-tmux-navigator'

call plug#end()
```

Source `.vimrc` and install:

```sh
:source ~/.vimrc # or :so
:PlugInstall
```

---

## Motions

Mesmerizing commands worth memorizing.

### Substitute

Original:

```sh
# i3wm config
bindsym XF86AudioRaiseVolume exec pactl set-sink-volume @DEFAULT_SINK@ +5%
bindsym XF86AudioLowerVolume exec pactl set-sink-volume @DEFAULT_SINK@ -5%
bindsym XF86AudioMute exec pactl set-sink-volume @DEFAULT_SINK@ toggle
```

Converted:

```hyprlang
# hyprland config
bind = ,XF86AudioRaiseVolume, exec, pactl set-sink-volume @DEFAULT_SINK@ +5%
bind = ,XF86AudioLowerVolume, exec, pactl set-sink-volume @DEFAULT_SINK@ -5%
bind = ,XF86AudioMute, exec, pactl set-sink-volume @DEFAULT_SINK@ toggle
```

The command:

```vim
:s/bindsym \(.*\) exec \(.*\)/bind = ,\1, exec,\2/
```

| Elements             | Explanation                                           |
| -------------------- | ----------------------------------------------------- |
| `:s`                 | substitute                                            |
| `/`                  | start of search pattern                               |
| `bind = \(.*\) exec` | between "bindsym" and "exec" into capture group `\1`  |
| `\(.*\)`             | strings after "exec" to the second capture group `\2` |
| `/`                  | start of replacement                                  |
| `bind = , \1`        | capture group 1 after `bind = ,`                      |
| `, exec, \2`         | capture group 2 after `, exec,`                       |
| `/`                  | end of command                                        |

---

### Global

```vim
:g/<pattern>/<cmd>
```

### Print

`p` at cmd, or nothing, will print by default.

### Delete

Delete every line with a matching pattern:

```vim
:g/vscode/d

" case insensitive with "i" option
:g/vscode/id
```

### Normal

You can use the `normal` command with `global`:

```vim
:g/neovim/norm A is awesome
```

- Add `A is Awesome` at the end of lines that contain `neovim`.

### Reverse

Delete every line that does not contain the string `vim`:

```vim
:v/vim/d
```

---

### Refactoring

- [3 Levels of Vim Refactoring - typecraft](https://www.youtube.com/watch?v=oQB8lYUZtrY)

### Find RegEx from File Types

```sh
:vimgrep /kr.or.iei/ `find . -type f`
```

### Open Quick-fix List

```sh
:copen
```

### Edit Quick-fix List with Substitute

```sh
:cdo %s/kr.or.iei/com.unemotioned/gc
```
