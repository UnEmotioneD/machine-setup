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
> `reagentc` must be disabled before deleting recovery partition.

```powershell
del part override
```

now you can expand the empty space next to `C:` partition

---

## Recover

Create 1GB of partition from `Disk Manager`.

> [!TIP]
> Do not assign letter to skip the **Remove Partition Letter** step.

From diskpart select the created partition.

Then assign previously used `ID` and `Attributes` values:

```powershell
set id={copied-id-value}

gpt attributes={copied-attirb-value}

reagentc /enable
```

---

## Remove Partition Letter

New recovery partition is visible from the file explorer.

Remove letter from the recovery volume:

```powershell
list volume

sel volume D

remove letter=D

exit
```
