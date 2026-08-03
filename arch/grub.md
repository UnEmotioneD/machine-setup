# Grub

Customize grub menu to have bigger text and just the items you need

- [Hide Unnecessary Items](#hide-unnecessary-items)
- [Reorder Items](#reorder-items)
- [Cleaner Menu](#cleaner-menu)
- [Menu Resolution](#menu-resolution)
- [Reboot to Last OS](#reboot-to-last-os)
- [Update Config](#update-config)

---

## Hide Unnecessary Items

Location of grub menu entries: `/etc/grub.d/`

```sh
cd /etc/grub.d
ls -a
```

example outputs:

```sh
00_header
05_debian_theme
10_linux        # Linux
30_os-prober    # Windows
```

Remove execute permission from scripts to hide:

```sh
sudo chmod -x {name of script}
```

---

## Reorder Items

Change index from `30_` to `09_` to put it above `10_linux`

```sh
sudo mv 30_os-prober 09_os-prober
```

> [!NOTE]
> `os-prober` is `Windows Boot Manager` in grub boot menu.

---

## Cleaner Menu

Grub config file: `/etc/default/grub`

```sh
sudo nvim /etc/default/grub
```

For cleaner menu add line

```conf
GRUB_DISABLE_SUBMENU=y
```

Uncomment following lines

```conf
GRUB_DISABLE_LINUX_UUID=true

GRUB_DISABLE_RECOVERY="true"
```

---

## Menu Resolution

from grub menu press `c` to go into terminal

- Newer BIOS

```sh
videoinfo
```

- Older BIOS

```sh
vbeinfo
```

from the supported resolutions select one

- lower resolution have lower input delay and bigger texts

back into the grub config file `/etc/default/grub`

- from auto to desired option:

```console
GRUB_FGXMODE=640x480
```

---

## Reboot to Last OS

```conf
GRUB_DEFAULT=saved

# add if needed
GRUB_SAVEDEFAULT=true
```

---

## Update Config

### Arch

```sh
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

### Ubuntu

```sh
sudo update-grub
```
