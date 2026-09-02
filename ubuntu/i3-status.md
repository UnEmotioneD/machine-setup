# i3 Status

Default status bar for i3wm.

---

## Config File

Copy the default config to `~/.config/i3status`:

```sh
mkdir -p ~/.config/i3status
cp /etc/i3status.conf ~/.config/i3status/config
```

---

## Autostart

Inside `~/.config/i3/config`:

```conf
bar {
        status_command i3status
        tray_output primary  # show status bar only on primary monitor
}
```

---

## Alternatives

- [i3status-rs](https://github.com/greshake/i3status-rust)
- [i3blocks](https://github.com/vivien/i3blocks)
