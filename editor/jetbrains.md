# [JetBrains](https://account.jetbrains.com/)

## Table of Contents

- [Shortcuts](#shortcuts)
- [Plugins](#plugins)
- [Settings](#settings)
  - [Tree Indent Guides](#tree-indent-guides)
  - [Inlay Usage & Code Author](#inlay-usage--code-author)
  - [Fold One-line Methods](#fold-one-line-methods)
  - [Caret Blink](#caret-blink)
  - [Scroll Pass BOF](#scroll-pass-bof)
  - [Smooth Scrolling](#smooth-scrolling)
  - [Sticky Lines](#sticky-lines)
  - [Palantir Java Format](#palantir-java-format)
- [Keymap](#keymap)
  - [Lookup](#lookup)

---

## Shortcuts

| Action               | Windows / Linux        | macOS                 |
| -------------------- | ---------------------- | --------------------- |
| Search Everywhere    | Shift + Shift          | -                     |
| Search File          | Ctrl + Shift + N       | Cmd + Shift + O       |
| Search Symbol        | Ctrl + Alt + Shift + N | Opt + Cmd + O         |
| Search Text          | Ctrl + Alt + Shift + E | Opt + Cmd + Shift + E |
| Run Everything       | Shift + F10            | Ctrl + Opt + R        |
| Project              | Alt + 1                | Cmd + 1               |
| Run                  | Alt + 4                | Cmd + 4               |
| Problem              | Alt + 6                | Cmd + 6               |
| Find Usage           | Alt + F7               | Opt + F7              |
| Rename               | Shift + F6             | -                     |
| Format               | Ctrl + Alt + L         | Opt + Cmd + L         |
| Generate Code        | Alt + Insert           | Cmd + N               |
| Next Error           | F2                     | -                     |
| Prev Error           | Shift + F2             | -                     |
| Show Context Actions | Alt + Enter            | Opt + Enter           |

> [!NOTE]
> `-` means same.

---

## Plugins

- [IdeaVim](https://github.com/jetbrains/ideavim)
- [IdeaVim-Quickscope](https://plugins.jetbrains.com/plugin/19417-ideavim-quickscope)
- [IdeaVim-EasyMotion](https://plugins.jetbrains.com/plugin/13360-ideavim-easymotion/versions)
- [AceJump](https://github.com/acejump/AceJump)
- [Catppuccin Theme](https://plugins.jetbrains.com/plugin/18682-catppuccin-theme)
- [Atom Material Icons](https://plugins.jetbrains.com/plugin/10044-atom-material-icons)

---

## Settings

### Tree Indent Guides

Settings > Appearance & Behavior > **Appearance** > _Tree Views_ > `Show indent guides`

### Inlay Usage & Code Author

Settings > Editor > **Inlay Hints** > _Code vision_ > `Usages`, `Code author`

### Fold One-line Methods

Settings > Editor > General > **Code Folding** > Fold by default: > _Java_ > `One-line methods`

### Caret Blink

Settings > Editor > General > **Appearance** > `Caret blinking (ms):`

### Scroll Pass BOF

Settings > Editor > **General** > _Virtual Space_ > `Show virtual space at the bottom of the file`

### Smooth Scrolling

Settings > Editor > **General** > _Scrolling_ > `Enable smooth scrolling`

### Sticky Lines

Settings > Editor > **General** > _Sticky Lines_ > `Show sticky lines while scrolling`

### Palantir Java Format

1. Install the `palantir-java-format` plugin.
2. Settings > **Other Settings** > `Enable palantir-java-format Settings`

---

## Keymap

### Lookup

Same as auto suggestion or completion.

1. Settings > **Keymap** > Search `Lookup`
2. Remap `Choose Lookup Item Replace`, `Select Next Completion Option` and `Select Previous Completion Option` &rarr; `Ctrl` + `Y`, `J` and `K`

> [!NOTE]
> For some reason `Ctrl + Y` remap is not working.
