# Korean

Korean input with Fcitx5 on Arch Linux and Hyprland.

## Table of Contents

- [Prerequisite](#prerequisite)
- [Environment Variables](#environment-variables)
- [Autostart](#autostart)
- [Configure](#configure)

---

## Prerequisite

- `Adobe fonts`: For proper font rendering on browsers.

```sh
sudo pacman -S adobe-source-han-sans-kr-fonts adobe-source-han-serif-kr-fonts
```

- `Fcitx5`: A modern input method framework.

```sh
yay -S fcitx5-im fcitx5-hangul fcitx5-configtool
```

---

## Environment Variables

Inside `.profile` or `.zprofile`:

```sh
export GLFW_IM_MODULE=fcitx
export GTK_IM_MODULE=wayland
export QT_IM_MODULE=wayland
export SDL_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
```

---

## Autostart

Inside the `Autostart` module of `~/.config/hyprland`.

```lua
hl.on('hyprland.start', function()
    -- ...
    hl.exec_cmd('fcitx5 -d')
    -- ...
end)
```

---

## Configure

Launch `fcitx5-configtool`.

### Input Method Tab

- Add `Hangul` to the **Current Input Method** list.

### Global Options Tab

- Set `Trigger Input Method` to **Right Alt (R_Alt)**
- Disable `Show Input Method Information when switch input method`.

![fcitx-config-global-options](../assets/fcitx-config-global-options.png)
