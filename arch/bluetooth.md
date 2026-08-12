# Bluetooth

## Reference

- [How to Use Bluetooth on Arch Linux - Eric Murphy](https://www.youtube.com/watch?v=rOL-T31l0lQ)

---

## Prerequisite

- `bluez`: bluetooth

```sh
sudo pacman -S bluez
```

---

## Enable Service

check if bluetooth module is running:

- `btusb`: allow bluetooth hardware connected via usb

```sh
lsmod | grep btusb
```

start if not running:

```sh
sudo modprobe btusb
```

enable service:

```sh
sudo systemctl enable --now bluetooth.service
```
