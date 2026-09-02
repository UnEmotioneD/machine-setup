# Touchpad

Enable tap to touch.

---

## Find Product

Get the device name:

```sh
grep -i touchpad /proc/bus/input/devices
```

Example output:

```sh
N: Name="MSNB0001:00 06CB:7E7E Touchpad"
```

---

## Config

Create config file:

```sh
sudo touch /etc/X11/xorg.conf.d/30-touchpad.conf
```

Add following content to the file.

```conf
Section "InputClass"
    Identifier "Touchpad"
    MatchProduct "MSNB0001:00 06CB:7E7E Touchpad"
    MatchIsTouchpad "on"
    Driver "libinput"

    Option "Tapping" "on"
    Option "TappingButtonMap" "lrm"
    Option "ClickMethod" "clickfinger"
    Option "NaturalScrolling" "true"
    Option "DisableWhileTyping" "true"
EndSection
```

- `1 finger tap` -> **left click**
- `2 finger tap` -> **right click**
- `3 finger tap` -> **middle click**

Restart for changes to take effect.
