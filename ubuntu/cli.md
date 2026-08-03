# Command Line Interface

## Table of Contents

- [tmux](#tmux)
- [bat](#bat)
- [delta](#delta)

---

APT installable packages

```sh
sudo apt install git curl stow tmux bat eza zoxide git-delta pavucontrol
```

---

## TMUX

Terminal Multi Plexer

Clone TPM(tmux plugins manager) for use

`~/.tmux/plugins`: where plugins will be installed

```sh
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

- Inside tmux session `prefix + I` to install plugins.
- `prefix + U` to update plugins.

---

## Bat

Better file previewer

### Install Bat

```sh
sudo apt install bat
```

### Create Bat Theme Directory

```sh
mkdir -p "$(bat --config-dir)/themes" # ~/.config/bat/themes
cd "$(bat --config-dir)/themes"
```

### Install Bat Theme

From the themes directory download a theme

- `tokyonight_storm` theme for sublime

```sh
curl -O https://raw.githubusercontent.com/folke/tokyonight.nvim/main/extras/sublime/tokyonight_storm.tmTheme
```

### Use Bat

Inside `.bashrc` or `.zshrc` set bat to use installed theme

```sh
export BAT_THEME=tokyonight_storm
```

Additionally set alias:

```sh
alias bat='batcat'
```

Create cache to use the theme:

```sh
bat cache --build
```

Test it:

```sh
bat ~/.bashrc
```

---

## Delta

[delta / GitHub](https://github.com/dandavison/delta)

add the following to `~/.gitconfig` customize `delta`

```gitconfig
[core]
  pager = delta
[merge]
  conflictstyle = zdiff3
[diff]
  colorMoved = default
[interactive]
  diffFilter = delta --color-only
[delta]
  # use n / N to move between diff sections
  navigate = true
  side-by-side = true
  line-numbers = true
  syntax-theme = tokyonight_storm
```
