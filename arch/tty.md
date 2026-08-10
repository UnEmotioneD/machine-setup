# TeleTypeWriter

- Originally physical typewriter terminals connected to computers
- Now virtual consoles built into Linux that provide a basic text interface
- Completely separate from your graphical desktop

| When                              | Why                                  |
| --------------------------------- | ------------------------------------ |
| Graphical session crashes/freezes | Fix it from TTY                      |
| Hyprland/Wayland won't start      | Debug from TTY without a GUI         |
| Display manager broken            | Log in and fix configs from TTY      |
| Running heavy tasks               | Avoid overhead of GUI                |
| System maintenance                | pacman updates, editing config files |
| No GUI available                  | Servers, minimal installs            |

---

## Keyboard Shortcut

`Ctrl + Alt` + **F1 ~ F7**

---

## Terminal Command

Switch to `TTY2`:

```sh
chvt 2
```

---

## TTY 1 through 7

- `tty1`: Default. Used for hyprland.
- `tty2`: Used for display managers such as **SDDM** and may not work properly.
- `tty3 ~ 7`: Available as normal TTY.
