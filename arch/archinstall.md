# Arch Install

## Reference

[How to Dual Boot Arch Linux and Windows 11 - Ksk Royal](https://www.youtube.com/watch?v=BB_SnWBQ6xw)

## Table of Contents

- [Before Install](#before-install)
  - [Create Disk Space](#create-disk-space)
  - [Enter BIOS](#enter-bios)
- [Live Environment](#live-environment)
  - [Set Font](#set-font)
  - [Wi-Fi with iwctl](#wi-fi-with-iwctl)
  - [Sync to DB](#sync-to-db)
  - [Partition](#partition)
  - [Format Partitions](#format-partitions)
  - [Mount Partitions](#mount-partitions)
  - [Start Install](#start-install)
  - [GRUB](#grub)
- [Login to Hyprland](#login-to-hyprland)
  - [Wi-Fi with Nmcli](#wi-fi-with-nmcli)
  - [OS Prober](#os-prober)
- [Nuke](#nuke)
  - [Delete Arch](#delete-arch)
  - [Clear Installation USB](#clear-installation-usb)

---

## Before Install

### Create Disk Space

use windows `disk manager` to create at least 40gb of free space

### Enter Bios

thinkpad: from boot screen `enter` &rarr; `f1`

```sh
security > secure boot
```

- secure boot: off
- clear all secure boot keys
- allow microsoft 3rd party uefi ca: off
- save and restart: `f10`

press enter again then `f12` select the drive with arch iso

select first boot option

---

## Live Environment

### Set Font

```sh
setfont ter-132n
```

---

### Wi-Fi with iwctl

```sh
iwctl
```

show machine's network interface

```sh
device list
```

show list of wi-fi networks

```sh
station wlan0 get-networks
```

connect to wi-fi

```sh
station wlan0 connect "{name of wi-fi}"
```

exit `iwd` check connection with `ping`

---

### Sync to DB

Install and update `archlinux-keyring` and `archinstall` script

```sh
pacman -Sy archlinux-keyring archinstall
```

To proceed type `y` or just press `enter`

---

### Partition

```sh
lsblk
```

could be `nvme0` or `sda` depending on the hardware

`cfdisk` into the drive

```sh
cfdisk /dev/nvme0n1
```

1. select `free space` then `new`

2. allocate `1G` and change `type` to `efi`

3. allocate every `free space` as `linux filesystem`

4. select `write` and type `yes`

5. Quit

---

### Format Partitions

check created partitions with `lsblk`

`efi` partition to `fat`

```sh
mkfs.fat -F32 /dev/nvme0n1p5
```

`root` partition to `ext4`

```sh
mkfs.ext4 /dev/nvme0n1p6
```

---

### Mount Partitions

```sh
mount /dev/nvme0n1p6 /mnt
mkdir /mnt/boot
mount /dev/nvme0n1p5 /mnt/boot
```

confirm with `lsblk`

| NAME      | MOUNTPOINTS |
| --------- | ----------- |
| nvme0n1p5 | /mnt/boot   |
| nvme0n1p6 | /mnt        |

---

### Start Install

execute:

```sh
archinstall
```

use arrow or `hjkl` to navigate

- mirrors: `South Korea` (search with `/`)

- disk configuration
  - partitioning
    - pre-mounted configuration
      - type `/mnt` which is where root partition is mounted to

- bootloader: `Grub`

- Authentication
  - Root password

  - user account
    - Add a user and set it up as superuser then confirm and exit

- profile &rarr; type &rarr; desktop
  select `Hyprland`
  - Seat access: `polkit`
  - select graphics driver

- Applications
  - Bluetooth: Enabled
  - Audio: `pipewire`
  - Print service: Enabled
  - Power management: `power-profiles-daemon`

- Network configuration: `Use Network Manager (default ...)`

- Timezone: `Asia/Seoul`

leave other options as is and select `Install`

After installation is complete choose the following option:
`chroot into installation for post-installation configurations`

---

### GRUB

Because the install script may have not installed grub properly

```sh
pacman -Syu grub efibootmgr dosfstools mtools
```

install grub into /boot partition

```sh
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB
```

generate and update grub config file

```sh
grub-mkconfig -o /boot/grub/grub.cfg
```

`exit` the chroot environment

now you can exit root session shutdown with `shutdown now` and remove the usb drive

---

## Login to Hyprland

from the login window change the session from `Hyprland(uwsm-managed)` which is
selected by default to just
`Hyprland`

### Wi-Fi with nmcli

install `networkmanager`

```sh
sudo pacman -S networkmanager
```

start and enable to start it every time

```sh
sudo systemctl enable --now NetworkManager
```

check searched wi-fi

```sh
nmcli device wifi list
```

connect to wi-fi

```sh
nmcli device wifi connect "{wifi-name}" password "{password}"
```

check connection

```sh
nmcli connection show
```

---

### OS Prober

noticed that there was no option to boot into windows in grub menu

enter into root mode

```sh
sudo -s
```

```sh
nvim /etc/default/grub
```

`GRUB_TIMEOUT=30`

at the bottom uncomment the `GRUB_DISABLE_OS_PROBER=false`

```sh
pacman -Sy os-prober
```

update the grub configurations

```sh
grub-mkconfig -o /boot/grub/grub.cfg
```

you should see:

```bash
found windows boot manager on /dev/nvme0n1p1@/efi/microsoft/boot/bootmgfw.efi
```

now you can choose to boot into windows

---

## Nuke

### Delete Arch

you can't remove efi partition from `disk management`

to delete the boot efi partition open cmd as admin

```sh
diskpart
```

show all the drives connected to pc

```sh
list disk
```

select disk

```sh
select disk 0
```

and list all the partitions

```sh
list partition
```

select and delete partition 5 which is efi for arch linux

```sh
delete partition override
```

---

### Clear Installation USB

select usb with `diskpart`

remove all partitions

```sh
clean
```

create new partition

```sh
create partition primary
```

format the partition

```sh
format fs=exfat quick
```

give the partition a letter

```sh
assign
```

exit out of `diskpart`

```sh
exit
```

- aliases
  - select: `sel`
  - delete: `del`
  - partition: `part`
