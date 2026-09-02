# Neovim

Build from source to get the latest versions on Ubuntu.

## Table of Contents

- [Dependencies](#dependencies)
- [Build](#build)
- [Update](#update)
- [Uninstall](#uninstall)

---

## Dependencies

- nerd fonts
- ripgrep
- nodejs
- npm
- bun
  - github-preview
- python3-full
  - clang-format
- openjdk-25-jdk
  - nvim-java

```sh
sudo apt install ripgrep nodejs npm python3-full openjdk-25-jdk

# install bun
curl -fsSL https://bun.sh/install | bash
```

---

## Build

If neovim is already installed with apt, remove it before build.

```sh
sudo apt remove neovim
```

### Prerequisite

```sh
sudo apt install ninja-build gettext cmake curl build-essential git
```

### Install

```sh
# clone
git clone https://github.com/neovim/neovim
cd neovim

git checkout stable # or nightly
make CMAKE_BUILD_TYPE=RelWithDebInfo
sudo make install

# check
nvim --version
```

---

## Update

```sh
cd neovim

git pull
make distclean  # recommended after major updates
make CMAKE_BUILD_TYPE=Release
sudo make install
```

---

## Uninstall

```sh
cd neovim

sudo rm -rf /usr/local/bin/nvim
sudo rm -rf /usr/local/lib/cmake/nvim
sudo rm -rf /usr/local/lib/nvim
sudo rm -rf /usr/local/share/nvim
```
