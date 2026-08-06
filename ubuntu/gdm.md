# Gnome Desktop Manager

Settings for GDM environment.

## Table of Contents

- [Setting](#setting)
- [Korean Input](#korean-input)
- [Recommended Packages](#recommended-packages)
- [Deb Packages](#deb-packages)

---

## Setting

- display
  - resolution
  - refresh rate

- power
  - power mode: performance
  - screen blank: never

- ubuntu desktop
  - position of new icons: top left
  - auto-hide dock: on
  - panel mode: off
  - position on screen: bottom
  - configure dock behavior
    - include unmounted volume: uncheck

- mouse & trackpad
  - 10cm from edge to edge horizontally
  - disable `Mouse Acceleration`

- appearance
  - style: dark

- accessibility
  - typing
    - typing assist
      - repeat keys
        - speed: fast
        - delay: short

---

## Korean Input

From `gnome-terminal`

```sh
sudo apt install ibus-hangul
```

Reboot for the right option to show up

- settings
  - keyboard
    - add input source
      - korean(hangul)

- korean(hangul) 3-dot menu
  - preference
    - hangul toggle key: right alt(remove other keys)
      - remove english(us) from input source

### Keyboard Shortcuts

In debian/ubuntu windows key is called `super`

- terminal: super + enter
- browser: super + b
- search: alt + space

- To disable
  - hide window: super + h
  - logout: super + l

---

## Recommended Packages

- git
- curl
- build-essential

```sh
sudo apt install git curl build-essential
```

---

## Deb Packages

- google chrome
- visual studio code
- slack

Download files with `.deb` which is for debian/ubuntu

cd into downloads directory from terminal

```sh
cd Downloads/
```

Install with dpkg(debian package) command

```sh
sudo dpkg -i {name of the .deb file}
```

You can pass multiple file names as arguments for `dpkg` command

- to run ipynb file from vscode install `pip3` and `ipykernel`
  - `ipykernel`: to run from locally from vscode
  - `jupyter`: to run from venv

```sh
sudo apt install python3-pip python3-ipykernel
```
