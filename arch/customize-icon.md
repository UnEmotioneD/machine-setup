# Customize Icon

Customize application's icon by override system-wide desktop entries with user-specific desktop entries.

---

## Copy Desktop Entry

```sh
# create local applications directory
mkdir -p ~/.local/share/applications

# copy application's desktop entry (example: kitty)
cp /usr/share/applications/kitty.desktop ~/.local/share/applications
```

---

## Edit Icon Path

Inside the copied desktop file, replace the value of `Icon` to point to your
custom icon's path.

From this:

```desktop
Icon=Kitty
```

To this:

```desktop
Icon=/home/unemotioned/.icons/kitty-icon.png
```

> [!NOTE]
> Use `/home/<user-name>` for home directory instead of `~`, since it does not
> get expanded

---

## Update Desktop Database

```sh
update-desktop-database ~/.local/share/applications
```
