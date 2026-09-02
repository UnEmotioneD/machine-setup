# Format USB

From install media to normal storage USB on Arch.

## Table of Contents

- [Prerequisite](#prerequisite)
- [1. Check USB Partition](#1-check-usb-partition)
- [2. Unmount Partitions](#2-unmount-partitions)
- [3. New Partition Table](#3-new-partition-table)
- [4. Format Partition](#4-format-partition)

---

## Prerequisite

- `exfatprogs`: exFAT utility

```sh
sudo pacman -S exfatprogs
```

---

## 1. Check USB Partition

```sh
lsblk
```

Example output:

```sh
NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS
sda           8:0    1 114.6G  0 disk
├─sda1        8:1    1   6.2G  0 part
├─sda2        8:2    1     5M  0 part
├─sda3        8:3    1   300K  0 part
└─sda4        8:4    1 108.4G  0 part
```

---

## 2. Unmount Partitions

Unmount all partitions inside the USB:

```sh
sudo umount /dev/sda*
```

---

## 3. New Partition Table

```sh
sudo fdisk /dev/sda
```

1. Press `g`: new GPT partition
2. Press `n`: new partition
3. Press `Enter` x3: USB into one partition
4. Press `w`: write and exit

---

## 4. Format Partition

```sh
sudo mkfs.exfat /dev/sda1
```
