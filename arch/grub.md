# Grub

Customize the GRUB menu to have bigger text and just the items you need.

## Table of Contents

- [Hide Unnecessary Items](#hide-unnecessary-items)
- [Reorder Items](#reorder-items)
- [Cleaner Menu](#cleaner-menu)
- [Menu Resolution](#menu-resolution)
- [Reboot to Last OS](#reboot-to-last-os)
- [Update Config](#update-config)

---

## Hide Unnecessary Items

Location of GRUB menu entries: `/etc/grub.d/`

```sh
cd /etc/grub.d
ls -a
```

Example outputs:

```sh
00_header
05_debian_theme
10_linux        # Linux
30_os-prober    # Windows
```

Remove execute permission from scripts to hide:

```sh
sudo chmod -x <file-name>
```

---

## Reorder Items

Change index from `30_` to `09_` to put it above `10_linux`.

```sh
sudo mv 30_os-prober 09_os-prober
```

> [!NOTE]
> `os-prober` is `Windows Boot Manager` in the GRUB boot menu.

---

## Cleaner Menu

GRUB config file: `/etc/default/grub`

```sh
sudo nvim /etc/default/grub
```

For a cleaner menu, add this line:

```conf
GRUB_DISABLE_SUBMENU=y
```

Uncomment the following lines:

```conf
GRUB_DISABLE_LINUX_UUID=true

GRUB_DISABLE_RECOVERY="true"
```

---

## Menu Resolution

From the GRUB menu, press `c` to go into the terminal.

- Newer BIOS

```sh
videoinfo
```

- Older BIOS

```sh
vbeinfo
```

From the supported resolutions, select one.

> [!TIP]
> Lower resolutions have lower input delay and bigger texts.

Back into the GRUB config file `/etc/default/grub`.

- From auto to the desired option:

```conf
GRUB_GFXMODE=640x480
```

---

## Reboot to Last OS

Automatically have the last boot method selected on the GRUB menu.

```conf
GRUB_DEFAULT=saved

# add if needed
GRUB_SAVEDEFAULT=true
```

---

## Update Config

- Arch

```sh
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

- Ubuntu

```sh
sudo update-grub
```
