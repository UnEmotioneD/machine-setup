# Format USB

USB with an `ISO` back to normal.

---

## Prerequisite

- `exfatprogs`: exFAT utility

```sh
sudo pacman -S exfatprogs
```

---

## Check USB Partition

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

## Unmount Partitions

Unmount all partitions inside the USB:

```sh
sudo umount /dev/sda*
```

---

## New Partition Table

```sh
sudo fdisk /dev/sda
```

1. Press `g`: new GPT partition
2. Press `n`: new partition
3. Press `Enter` x3: USB into one partition
4. Press `w`: write and exit

---

## Format Partition

```sh
sudo mkfs.exfat /dev/sda1
```
