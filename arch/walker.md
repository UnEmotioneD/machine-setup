# Walker

A modern application launcher for Wayland.

## References

- [GitHub](https://github.com/abenz1267/walker)
- [Official Website](https://walkerlauncher.com/)

## Table of Contents

- [Install](#install)
- [Launch](#launch)

---

## Install

```sh
yay -S walker-bin
```

> [!WARNING]
> Do not install `elephant-bin` separately which will cause version mismatch.

### [Providers](https://walkerlauncher.com/docs/providers)

- Arch Linux (AUR)
- Bluetooth
- Calculator
- Clipboard
- Command Runner
- Symbols
- Web Search
- Windows

```sh
yay -S\
  elephant-archlinuxpkgs\
  elephant-bluetooth\
  elephant-calc\
  elephant-clipboard\
  elephant-runner\
  elephant-symbols\
  elephant-websearch\
  elephant-windows
```

### Restart

Restart `elephant` after installing providers:

```sh
pkill elephant
elephant & disown
```

---

## Auto Start

Inside `~/.config/hyprland/modules/autostart.lua`:

```lua
hl.on('hyprland.start', function()
  -- ...
  hl.exec_cmd('walker --gapplication-service')
  hl.exec_cmd('elephant')
  -- ...
end)
```

---

## Launch

By terminal commands or with Hyprland keybinds.

### Module Name

The module name is the string after the semicolon.

```sh
elephant listproviders
```

### Keybindings

Inside `~/.config/hyprland/modules/keybindings.lua`:

```lua
-- default walker
hl.bind(mainMod .. ' + D', hl.dsp.exec_cmd('walker'))

-- clipboard
hl.bind(mainMod .. ' + V', hl.dsp.exec_cmd('walker -m clipboard'))

-- calculator
hl.bind(mainMod .. ' + C', hl.dsp.exec_cmd('walker -m calc'))
```

`-m` is an alias of `--providers`.
