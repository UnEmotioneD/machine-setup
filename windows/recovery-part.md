# Windows Recovery Partition

How to remove and recover the `recovery partition`.

## Reference

[Fix "Can't Extend C Drive with Unallocated Space" in Windows 10/11 - Techy Druid](https://www.youtube.com/watch?v=K76z0gQm9oA)

## Table of Contents

- [Preparation](#preparation)
- [Delete](#delete)
- [Recover](#recover)
- [Remove Partition Letter](#remove-partition-letter)

---

## Preparation

open `cmd prompt` with admin privilege

```powershell
reagentc /disable

diskpart

list disk

# disk with windows installed
sel disk 0

list part

# select the recovery partition
sel part 4

detail part
```

copy the value of `Type` and `Attrib`

---

## Delete

> [!WARNING]
> `reagentc` must have been disabled before deleting recovery partition.

```powershell
del part override
```

now you can expand the empty space next to `C:` partition

---

## Recover

create 1GB of partition from disk manager

from diskpart select the created partition

and then:

```powershell
# set id
set id={copied-id-value}

# set attrib
gpt attributes={copied-attirb-value}
```

---

## Remove Partition Letter

new recovery partition is visible from the file explorer

```powershell
list volume

sel volume D

remove letter=D

exit

reagentc /enable
```
