# Rofi

Application launcher

## Install

`rofimoji`: nerdfonts and emojis

```sh
sudo apt install rofi rofi-calc rofimoji
```

## Usage

Execute the following with keybindings in i3 config

### Default Rofi

```sh
rofi -show drun -sort -theme ~/.config/rofi/theme.rasi
```

### Rofi Calculator

```sh
rofi -show calc -modi calc -no-show-match -calc-command "wl-copy {result}"\
  -theme ~/.config/rofi/theme.rasi
```
