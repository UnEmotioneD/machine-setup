# [Rofi](https://github.com/davatorium/rofi)

Application launcher.

---

## Install

- `rofimoji`: Nerd Fonts and emojis

```sh
sudo apt install rofi rofi-calc rofimoji
```

---

## Usage

Configure to use the following with keybinds from `~/.config/i3/config`.

### Minimal

```sh
rofi -show drun -sort -theme ~/.config/rofi/theme.rasi
```

### Calculator

```sh
rofi -show calc -modi calc -no-show-match -calc-command "wl-copy {result}" -theme ~/.config/rofi/theme.rasi
```
