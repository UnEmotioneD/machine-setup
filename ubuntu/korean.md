# Korean

How to setup korean(hangul) input on i3 with fcitx5.

---

## Install

```sh
sudo apt install fcitx5 fcitx5-hangul fcitx5-configtool

# recommended fonts
sudo apt install fonts-noto-cjk
```

---

## Environment Variables

Inside `.profile` or `.zprofile`:

```sh
export XMODIFIERS=@im=fcitx
export INPUT_METHOD=fcitx
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
```

---

## Fcitx5

1. Launch `fcitx5-config-qt`.
2. Search `hangul` from right side of window and move it to left.
3. From `global option` tab set **Right Alt** to change input source.
