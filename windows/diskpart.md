# Diskpart

## Table of Contents

- [Format USB](#format-usb)

---

## Format USB

```powershell
list disk

select disk <disk-no>

# remove every partitions
clean

create partition primary

select part 1

format fs=fat32 quick

assign

exit
```
