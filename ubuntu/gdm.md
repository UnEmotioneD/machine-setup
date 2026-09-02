# Gnome Desktop Manager

Settings for GDM environment.

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

Reboot for the `hangul` option to show up.

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
