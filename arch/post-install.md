# Post Install

## Reference

- [10 things you must do after installing arch linux (2023) - Ksk Royal](https://www.youtube.com/watch?v=odgD_RdJjCU)

## Table of Contents

- [Pacman](#pacman)
  - [I Love Candy](#i-love-candy)
  - [Mirror List](#mirror-list)
- [Additional Kernel](#additional-kernel)

---

## Pacman

### I Love Candy

Open `/etc/pacman.conf` with sudo privileges:

```sh
sudo nvim /etc/pacman.conf
```

Under `[options]` and `# Misc options`, uncomment `Color`.

Add `ILoveCandy` to make the download progress bar look like the Pac-Man game, then update pacman:

```sh
sudo pacman -Sy
```

### Mirror List

Install `reflector` with pacman:

```sh
sudo pacman -S reflector
```

Create a backup of the default mirror list:

```sh
sudo cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.bak
```

Then fetch the top 10 fastest servers:

```sh
sudo reflector --verbose --latest 10 --protocol https --sort rate --save /etc/pacman.d/mirrorlist
```

and update pacman again.

---

## Additional Kernel

Install LTS as a backup:

```sh
sudo pacman -S linux-lts linux-lts-headers
```

Update GRUB config:

```sh
sudo grub-mkconfig -o /boot/grub/grub.cfg
```
