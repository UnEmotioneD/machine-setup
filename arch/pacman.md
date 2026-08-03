# Pacman

how to use pacman

---

## Table of Contents

- [Install](#install)
- [Update](#update)
- [Remove](#remove)
  - [Remove orphaned](#remove-orphaned)
  - [Remove Dependencies](#remove-dependencies)
- [Search](#search)
  - [From Online](#from-online)
  - [From Installed](#from-installed)
- [Clear](#cleanup)

---

## Install

```sh
# normal install
sudo pacman -S vim

# without confirmation
sudo pacman -S --noconfirm neovim

# if not installed already
sudo pacman -S --needed emacs
```

---

## Update

```sh
# refresh package database only
sudo pacman -Sy

# full upgrade (recommended)
sudo pacman -Syu
```

---

## Remove

```sh
# just the specified package
sudo pacman -R nano

# with dependencies
sudo pacman -Rs nano

# with dependencies and config files
sudo pacman -Rns code
```

### Remove Orphaned

list orphaned

- `Q`: query
- `t`: unrequired packages
- `d`: dependencies only
- `q`: quiet output

```sh
pacman -Qtdq
```

remove orphaned with queried results

```sh
sudo pacman -Rns $(pacman -Qtdq)
```

### Remove Dependencies

see what package depends on it

```sh
pacman -Qi {pkg-name}
```

more cleaner way

```sh
pacman -r {pkg-name}
```

skip dependency check

`-d`: Skip dependency check
`-dd`: Skip all dependency check

```sh
sudo pacman -Rdd {pkg-name}
```

---

## Search

### From Online

```sh
pacman -Ss <pkg-name>
```

### From Installed

```sh
# query every installed packages
pacman -Q

# installed explicitly (not as dependency)
pacman -Qe

# dependencies only
pacman -Qd
```

---

## Cleanup

```sh
# remove outdated
sudo pacman -Sc

# remove all cached packages
sudo pacman -Scc
```
