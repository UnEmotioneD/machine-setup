# Remove Linux

Boot into Windows and remove Linux partition with `disk management`.

---

## Delete EFI

To delete the Linux's EFI partition open `cmd` with admin privilege.

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

To format USB from install media back to storage device checkout
[windows/format-usb](../windows/format-usb.md).
