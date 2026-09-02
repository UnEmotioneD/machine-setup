# Arch Install

Install [Arch Linux](https://archlinux.org/) with the [archinstall](https://github.com/archlinux/archinstall) script.

## Reference

- [How to Dual Boot Arch Linux and Windows 11 - Ksk Royal](https://www.youtube.com/watch?v=BB_SnWBQ6xw)

## Table of Contents

- [Preparation](#preparation)
  - [Create Disk Space](#create-disk-space)
  - [BIOS](#bios)
- [Live Environment](#live-environment)
  - [Set the Font](#set-the-font)
  - [Wi-Fi with IWCTL](#wi-fi-with-iwctl)
  - [Update and Install](#update-and-install)
  - [Create Partitions](#create-partitions)
  - [Format Partitions](#format-partitions)
  - [Mount Partitions](#mount-partitions)
  - [Start Install](#start-install)
  - [GRUB](#grub)
- [Hyprland](#hyprland)
  - [Wi-Fi with NMCLI](#wi-fi-with-nmcli)
  - [OS Prober](#os-prober)

---

## Preparation

### Create Disk Space

Use Windows `Disk Management` to create at least **40GB** of free space.

### BIOS

For ThinkPad:

- `secure boot`: `off`
- clear all secure boot keys
- `allow microsoft 3rd party uefi ca`: `off`

Boot into install media.

---

## Live Environment

### Set the Font

For better readability.

```sh
setfont ter-132n
```

### Wi-Fi with IWCTL

```sh
iwctl

# show network interface
device list

# show a list of wi-fi networks
station wlan0 get-networks

# connect to wi-fi
station wlan0 connect "<wifi-name>"

exit

# check connection
ping google.com
```

---

### Update and Install

Update pacman and install packages:

```sh
pacman -Sy archlinux-keyring archinstall
```

- `archlinux-keyring`: PGP keys for authenticating packages.
- `archinstall`: The install script.

---

### Create Partitions

List disks and partitions:

```sh
lsblk
```

> [!IMPORTANT]
> Disk names could be `nvme` or `sda` depending on the hardware.

`cfdisk` into the drive:

```sh
cfdisk /dev/nvme0n1
```

1. Select `free space` and then `new`.
2. Allocate `1G` and change `type` to `efi`.
3. Allocate every `free space` as `linux filesystem`.
4. Select `write` and type `yes`.
5. Quit.

---

### Format Partitions

Check created partitions with `lsblk` command.

Format `efi` partition to `fat`:

```sh
mkfs.fat -F32 /dev/nvme0n1p5
```

Format `root` partition to `ext4`:

```sh
mkfs.ext4 /dev/nvme0n1p6
```

---

### Mount Partitions

> [!NOTE]
> Mount `root` first, then `efi`. Mounting root on `/mnt` after EFI would hide `/mnt/boot`.

Mount `root` partition to `/mnt` directory:

```sh
mount /dev/nvme0n1p6 /mnt
```

Mount `efi` partition to `/mnt/boot` directory:

```sh
mkdir /mnt/boot
mount /dev/nvme0n1p5 /mnt/boot
```

Confirm with `lsblk`.

| NAME      | MOUNTPOINTS |
| --------- | ----------- |
| nvme0n1p5 | /mnt/boot   |
| nvme0n1p6 | /mnt        |

---

### Start Install

Execute:

```sh
archinstall
```

- Mirrors: `South Korea`
- Disk configuration
  - partitioning
    - pre-mounted configuration
      - type `/mnt`, which is where the root partition is mounted
- Bootloader: `Grub`
- Authentication
  - root password
  - user account
    - Add a user and set it up as a superuser, then confirm and exit
- Profile &rarr; type &rarr; desktop &rarr; select `Hyprland`
  - seat access: `polkit`
  - select graphics driver
- Applications
  - Bluetooth: Enabled
  - Audio: `pipewire`
  - Print service: Enabled
  - Power management: `power-profiles-daemon`
- Network configuration: `Use Network Manager (default ...)`
- Timezone: `Asia/Seoul`

Leave other options as is and select `Install`.

After installation is complete choose: `chroot into installation for post-installation configurations`.

---

### GRUB

Explicitly install GRUB since the script may not have installed it properly.

```sh
pacman -Syu grub efibootmgr dosfstools mtools

# install grub
grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB

# update grub config
grub-mkconfig -o /boot/grub/grub.cfg

# exit chroot
exit

shutdown now # remove the install media
```

---

## Hyprland

From the login window, change the session from `Hyprland (uwsm-managed)` to just `Hyprland`.

### Wi-Fi with NMCLI

```sh
# enable service now
sudo systemctl enable --now NetworkManager

# list scanned wi-fi networks
nmcli device wifi list

# connect
nmcli device wifi connect "<wifi-name>" password "<pw>"

# check connection
nmcli connection show
```

---

### OS Prober

Detect Windows with `os-prober` and add it to the GRUB menu.

```sh
sudo -E nvim /etc/default/grub
```

- Uncomment the following line:

```conf
GRUB_DISABLE_OS_PROBER=false
```

- Install:

```sh
sudo pacman -Sy os-prober
```

- Update GRUB config:

```sh
grub-mkconfig -o /boot/grub/grub.cfg
```

You should see:

```bash
found windows boot manager on /dev/nvme0n1p1@/efi/microsoft/boot/bootmgfw.efi
```

---

Check out [post-install](./post-install.md) for more.

To remove Linux, follow the instructions in [remove-linux](../windows/remove-linux.md).
