# Mount USB

Mount and unmount external drives from terminal.

## Table of Contents

- [Find External Drive](#find-external-drive)
- [Create Mount Directory](#create-mount-directory)
- [Mount](#mount)
- [Unmount](#unmount)

---

## Find External Drive

List block devices:

```sh
lsblk
```

Example output:

```text
sdb      # entire disk
└─sdb1   # partition on the external drive
```

> [!IMPORTANT]
> Device names `sdb` / `sdb1` are for example. Confirm the correct device on your system.

---

## Create Mount Directory

Create a directory where the drive will be mounted:

```sh
sudo mkdir -p /mnt/usb
```

---

## Mount

Mount the partition (most common case):

```sh
sudo mount /dev/sdb1 /mnt/usb
```

If the drive has no partitions, you may need to mount the disk itself:

```sh
sudo mount /dev/sdb /mnt/usb
```

---

## Unmount

by `mount point`:

```sh
sudo umount /mnt/usb
```

with `device name`:

```sh
sudo umount /dev/sdb1
```
