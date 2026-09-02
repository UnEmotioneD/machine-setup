# [TMUX](https://github.com/tmux/tmux)

Terminal Multiplexer.

## Table of Contents

- [Install with Package Manager](#install-with-package-manager)
  - [macOS](#macos)
  - [Arch Linux](#arch-linux)
  - [Ubuntu](#ubuntu)
- [TPM](#tpm)
- [Local Build](#local-build)
  - [1. Prerequisite](#1-prerequisite)
  - [2. Download](#2-download)
  - [3. Unzip Archive](#3-unzip-archive)
  - [4. Install](#4-install)
  - [Uninstall](#uninstall)

---

## Install with Package Manager

### macOS

`bash` for compatibility with 3rd party plugins.

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

[TMUX Plugin Manager](https://github.com/tmux-plugins/tpm)

### Clone

`~/.tmux/plugins`: where plugins will be installed.

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

---

## Local Build

Build `tmux` locally from an archive file.

### 1. Prerequisite

```sh
brew install pkgconf libevent ncurses autoconf
```

### 2. Download

Download `tar.gz` from [github release](https://github.com/tmux/tmux/releases).

### 3. Unzip Archive

Go to directory where the `tmux-x.x.tar.gz` is at unzip and move into it.

- `-x`: Extract files from the archive.
- `-z`: Decompress using gzip for `.gz` files.
- `-f`: Specifies the file to operate on (next arg is the archive name).

```sh
tar -zxf tmux-3.6b.tar.gz
cd tmux-3.6b
```

### 4. Install

```sh
./configure CPPFLAGS="-I/opt/homebrew/include" LDFLAGS="-L/opt/homebrew/lib" --enable-utf8proc
make && sudo make install
```

You can remove the archive and unzipped files after this.

---

### Uninstall

If you do `sudo make uninstall` at the unzipped archive directory it will prompt
to do the following.

```sh
sudo rm /usr/local/bin/tmux
```
