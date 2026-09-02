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
  - power mode: `performance`
  - screen blank: `never`
- ubuntu desktop
  - position of new icons: `top left`
  - auto-hide dock: `on`
  - panel mode: `off`
  - position on screen: `bottom`
  - configure dock behavior
    - include unmounted volume: disable
- mouse & trackpad
  - 10cm from edge to edge horizontally
  - disable `Mouse Acceleration`
- appearance
  - style: `dark`
- accessibility
  - typing
    - typing assist
      - repeat keys
        - speed: `fast`
        - delay: `short`

---

## Korean Input

From `gnome-terminal`:

```sh
sudo apt install ibus-hangul
```

Reboot for the right option to show up.

- settings
  - keyboard
    - add input source
      - `korean(hangul)`
- `korean(hangul)` 3-dot menu
  - preference
    - hangul toggle key: `right alt` (remove other keys)
      - remove `english(us)` from input source

### Keyboard Shortcuts

In Debian/Ubuntu the Windows key is called `Super`.

- terminal: `Super + Enter`
- browser: `Super + B`
- search: `Alt + Space`
- To disable
  - hide window: `Super + H`
  - logout: `Super + L`

---

## Recommended Packages

```sh
sudo apt install git curl build-essential
```

---

## Deb Packages

- Google Chrome
- Visual Studio Code
- Slack

Download files with `.deb`, which is for Debian/Ubuntu.

`cd` into the downloads directory from the terminal:

```sh
cd Downloads/
```

Install with the `dpkg` (Debian package) command:

```sh
sudo dpkg -i {name of the .deb file}
```

You can pass multiple file names as arguments to the `dpkg` command.

- To run an `.ipynb` file from VS Code, install `pip3` and `ipykernel`.
  - `ipykernel`: to run locally from VS Code
  - `jupyter`: to run from a venv

```sh
sudo apt install python3-pip python3-ipykernel
```
