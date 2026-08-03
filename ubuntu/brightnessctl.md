# Brightness Control

## Reference

[fix brightness ubuntu](https://itsfoss.com/fix-brightness-ubuntu-1310/)

---

## Find Graphics Card

```sh
ls /sys/class/backlight/
```

Output:

```text
intel_backlight
```

---

## Fix The Issue

Create configuration file:

```sh
sudo Touch /usr/share/X11/xorg.conf.d/20-intel.conf
```

open with sudo privilege

add the following content:

```conf
Section "Device"
        Identifier  "card0"
        Driver      "intel"
        Option      "Backlight"  "intel_backlight"
        BusID       "PCI:0:2:0"
EndSection
```

Logout and log back in for this to take effect

---

## i3 Brightness Config

control brightness with [`Brillo`](../arch/brillo.md)

```sh
bindsym XF86MonBrightnessUp   exec --no-startup-id brillo -q -u 1000 -A 1
bindsym XF86MonBrightnessDown exec --no-startup-id brillo -q -u 1000 -U 1
```
