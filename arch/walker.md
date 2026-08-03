# Walker

A modern application launcher

- [abenz1267/walker](https://github.com/abenz1267/walker)
- [walkerlauncher.com](https://walkerlauncher.com/)

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

Restart `elephant` elephant after installing providers

```sh
pkill elephant
elephant & disown
```

---

## Auto Start

```hyprlang
exec-once = walker --gapplication-service
exec-once = elephant
```

---

## Launch

### Module Name

The module name is string after semi-colon

```sh
elephant listproviders
```

### Keybindings

```hyprlang
bind = $mainMod, D, exec, walker
```

```hyprlang
bind = $mainMod, V, exec, walker -m clipboard
```

- `-m`: `--provider` alias
