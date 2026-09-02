# Mouse sensitivity

Change mouse sensitivity on Ubuntu and i3 machine.

---

## Create Config

Create config file:

```sh
sudo touch /etc/X11/xorg.conf.d/40-mouse.conf
```

---

## Configure

Add the following content:

```conf
Section "InputClass"
    Identifier "Disable accel and slow mouse"
    MatchIsPointer "on"
    Driver "libinput"
    Option "AccelProfile" "flat"
    Option "AccelSpeed" "-0.13"
EndSection
```

- `AccelSpeed -0.13`: Moving 800 DPI mouse 10cm makes the pointer to go from edge to edge on 27-inch QHD monitor.

> [!NOTE]
> Reboot for config to take effect.
