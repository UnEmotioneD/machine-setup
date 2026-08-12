# QMK

## Reference

- [Setting Up Your QMK Environment](https://docs.qmk.fm/newbs_getting_started)

## Table of Contents

- [1. Install](#1-install)
- [2. Setup](#2-setup)
- [3. Find Keyboard](#3-find-keyboard)
- [4. Create Keymap](#4-create-keymap)
- [5. Flash](#5-flash)
- [Troubleshooting](#troubleshooting)
  - [MODE Sonnet](#mode-sonnet)

---

## 1. Install

```sh
curl -fsSL https://install.qmk.fm | sh
```

---

## 2. Setup

```sh
qmk setup
```

---

## 3. Find Keyboard

Example: [MODE Sonnet](https://modedesigns.com/products/sonnet)

`mode/m75h` for hotswap

```sh
qmk list-keyboards | grep -i "mode/m75h"
```

---

## 4. Create Keymap

- `mode/m75h`: Result of `list-keyboards` command.
- `sonnet`: Name your choice. Which will the the final directory.

```sh
qmk new-keymap -kb mode/m75h -km sonnet
```

### Keymap Directory

Save this directory at somewhere.

```sh
/Users/unemotioned/qmk_firmware/keyboards/mode/m75h/keymaps/sonnet
```

### JSON to C

More features available in **C** file.

```sh
qmk json2c -o keymap.c keymap.json
```

### Compile

Save this command somewhere.

```sh
qmk compile -kb mode/m75h -km sonnet
```

---

## 5. Flash

Compile and flash if the keyboard is in bootloader mode.

```sh
qmk flash -kb mode/m75h -km sonnet
```

---

## Troubleshooting

### MODE Sonnet

The mode sonnet does not shows up on finder like other keyboards when reset
button is pressed.

#### [VIA](https://www.usevia.app/)

Enable QMK for VIA. So you can use both QMK and VIA for mapping keyboard

```make
VIA_ENABLE = yes
```

1. Map `Reset` key to layout
2. Compile the keymap into `.bin` file at `~/qmk_firmware`

#### [QMK Toolbox](https://qmk.fm/toolbox)

1. Select compiled `.bin` file at `~/qmk_firmware`
2. Select `ATmega32U2` for the `Sonnet`
3. Go into bootloader mode by pressing the `reset` key
4. Click the `Flash` button. (or check the `Auto-Flash` check box which will flash
   automatically when the keyboard goes into bootloader mode)
