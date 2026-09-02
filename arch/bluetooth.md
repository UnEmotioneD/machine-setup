# Bluetooth

## Reference

- [How to Use Bluetooth on Arch Linux - Eric Murphy](https://www.youtube.com/watch?v=rOL-T31l0lQ)

---

## Install

- `Arch`

```sh
sudo pacman -S bluez bluez-utils blueman
```

- `Ubuntu`

```sh
sudo apt install bluetooth bluez blueman
```

---

## Enable Service

```sh
sudo systemctl enable --now bluetooth
```
