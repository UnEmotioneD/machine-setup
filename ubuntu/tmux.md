# TMUX

[Terminal Multi Plexer](https://github.com/tmux/tmux)

---

## Install

### macOS

BASH for compatibility with 3rd party plugins.

```sh
brew install bash tmux
```

### Arch Linux

```sh
sudo pacman -S tmux
```

### Ubuntu

```sh
sudo apt install tmux
```

---

## TPM

[TMUX Plugins Manager](https://github.com/tmux-plugins/tpm)

### Clone

`~/.tmux/plugins`: where plugins will be installed

```sh
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

### Usage

Add following lines inside `~/.tmux.conf`:

```conf
set -g @plugin 'tmux-plugins/tpm'

# 3rd party plugins and its config goes here

# make sure this line is at bottom of file
run -b '~/.tmux/plugins/tpm/tpm'
```

### Keybinds

Inside tmux session:

- `prefix + I`: install plugins
- `prefix + U`: update plugins
