# Remove Linux

Boot into Windows and remove the Linux partition with Disk Management.

---

## Delete EFI

To delete Linux's EFI partition, open `cmd` with admin privilege.

```powershell
diskpart

list disk

# select the disk with arch installed
sel disk 0

list partition

# select the arch efi partition
sel part 5

# override protection
del part override

exit
```

To format the USB from install media back to a storage device, check out
[windows/format-usb](../windows/format-usb.md).
