# [Bat](https://github.com/sharkdp/bat)

A [cat](https://www.man7.org/linux/man-pages/man1/cat.1.html) clone with wings.

- Syntax highlighting
- Git integration

> [!NOTE]
> `cat` is not just an file previewer though.

## Table of Contents

- [Install](#install)
- [Theme](#theme)
- [Preparation](#preparation)
- [Usage](#usage)

---

## Install

Pacman:

```sh
sudo pacman -Syu bat

# check installed
bat --version
```

APT:

```sh
sudo apt install bat

# check installed
batcat --version
```

---

## Theme

Color schemes to use on code preview.

### Create Theme Directory

```sh
mkdir -p "$(bat --config-dir)/themes" # ~/.config/bat/themes
cd "$(bat --config-dir)/themes"
```

### Install Theme

From the themes directory download a theme

- `tokyonight_storm` theme for sublime

```sh
curl -O https://raw.githubusercontent.com/folke/tokyonight.nvim/main/extras/sublime/tokyonight_storm.tmTheme
```

---

## Preparation

Inside `.bashrc` or `.zshrc` set bat to use installed theme

```sh
export BAT_THEME=tokyonight_storm
```

Add alias on Debian/Ubuntu:

```sh
alias bat='batcat'
```

Build cache to use the theme:

```sh
bat cache --build
```

---

## Usage

```sh
bat ~/.zshrc
```
