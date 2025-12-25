# Improved Improved Improved Window Manager

## Referenced Video

- [Type craft](https://www.youtube.com/@typecraft_dev/featured)
  - [i3 pt1](https://www.youtube.com/watch?v=xWIDvnNFl5I)
  - [i3 pt2](https://www.youtube.com/watch?v=wXZgUudR41I)

- [Alex Booker](https://www.youtube.com/@bookercodes/videos)
  - [how to rice](https://www.youtube.com/watch?v=ARKIwOlazKI&t=126s)

## Install Packages

- `i3`: the window manager
  - `i3lock`: lock screen
  - `i3status`: statusbar
  - `dmenu`: app launcher
- `alacritty`: i3 sensible terminal
- `feh`: wallpaper
- `picom`: compsiter(fixes screen tearing)
- `rofi`: better app launcher
- `i3block`: better i3 status

```bash
sudo apt install -y i3 alacritty feh picom rofi i3block
```

---

## Start i3wm

- logout
- select i3

---

## Configure

- config file: `~/.config/i3/config`

---

## Key Binding

- Add this line to `config`

```text
focus_wrapping no
```

- windows key to mod
- mod + h, j, k, l for changing focus
- mod + y, u, i, o, p, n, m for workspaces
- screen shot

### Default Key

- mod + r: resize
- mod + s: stack mod
- mod + v: next window will open in vertical position

- mod + shift + r: reload i3 config
- mod + shift + q: quit app

- floating
- parent/child

---

## Status bar

- copy i3status config from `/etc/i3status.conf` to `~/.config/i3status/config`

```text
mkdir -p ~/.config/i3status
cp /etc/i3status.conf ~/.config/i3status/config
```

- left: workspaces
- right: input source, wifi, bluetooth, speaker, cpu, temperature, battery, time

---

## Wallpaper

- Launch `feh` on login

```text
exec_always --no-startup-id ~/.fehbg
exec_always feh --bg-scale {absolute path to the image}
```

---

## App Launcher

- r_alt + space

- dmenu
- rofi(better app launcher)

### Power menu

```bash
mkdir -p ~/.config/rofi
cd ~/.config/rofi
toch powermenu.sh
```

```text
#!/bin/bash

options=" Lock\n󰗽 Logout\n Reboot\n Shutdown"

chosen=$(echo -e "$options" | rofi -dmenu -p "Power")

case "$chosen" in
    *Lock*) i3lock ;;
    *Logout*) i3-msg exit ;;
    *Reboot*) systemctl reboot ;;
    *Shutdown*) systemctl poweroff ;;
esac
```

```bash
chmod +x ~/.config/rofi/powermenu.sh
```

- Bind in i3 config

```text
bindsym $mod+Shift+q exec ~/.config/rofi/powermenu.sh
```

---

## Assign App to Workspace

- Use `xprop` to get app's class name

```text
assign [class="google-chrome"] $ws2
assign [class="Alacritty"] $ws3
assign [class="Code"] $ws4
```

---

## Multiple Monitor

- Assign workspace `7` or `y` to secondary monitor

---

## i3lock

- change bg color
- show input field
