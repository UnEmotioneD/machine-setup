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

Check if the bluetooth module is running:

- `btusb`: allow bluetooth hardware connected via USB

```sh
lsmod | grep btusb
```

Start if not running:

```sh
sudo modprobe btusb
```

Enable the service:

```sh
sudo systemctl enable --now bluetooth.service
```
