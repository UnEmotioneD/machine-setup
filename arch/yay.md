# Yay

`Arch User Repository` helper.

## Reference

[How to install and use yay: The best AUR Helper for Arch Linux - DenshiVideo](https://www.youtube.com/watch?v=NzNuFN9hqjI)

---

## Prerequisite

```sh
sudo pacman -S git
```

---

## Install

```sh
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```

- `-s`: download all the dependencies
- `-i`: automatically install it with pacman

---

## Check

Also updates yay itself and upgrades other packages.

```sh
yay
```

---

### Clean Build

Delete old build files rebuild from scratch.
Prevents issues by leftover files or outdated libraries.

### Diffs to Show

Show changes in PKGBULID before building AUR packages.
For `security` and `transparency`

You can review:

- new or removed commands
- changes in dependencies

> [!TIP]
> For normal use just choose `None` for both.
