# Format USB

From install media to normal storage USB.

> [!WARNING]
> The `clean` command will permanently delete all data.

```powershell
diskpart

list disk

# select the USB
select disk <disk-no>

# remove every partitions
clean

create partition primary

# select the new partition
select part 1

# quick format partitions
format fs=exfat quick

# assign letter
assign

exit
```
