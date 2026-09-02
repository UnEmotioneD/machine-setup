# Bluetooth

From `gnome-desktop` if bluetooth does not toggle on.

---

## Install

- `bluetooth`: systemd integration
- `bluez`: tool + daemon
- `blueman`: GUI manager

```sh
sudo apt install bluetooth bluez blueman
```

---

## Start Service

```sh
systemctl enable --now bluetooth
```
