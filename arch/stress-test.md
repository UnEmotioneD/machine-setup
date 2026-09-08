# Stress Test

Stress test CPU with [stress-ng](https://github.com/ColinIanKing/stress-ng).

---

## Install

`lm_sensors`: Temperature monitoring.

```sh
sudo pacman -Syu stress-ng lm_sensors
```

---

## Test

`--cpu 0`: All available CPU cores.

```sh
stress-ng --cpu 0 --timeout 1m
```

---

## Temperature

Refresh `sensor` every second.

```sh
watch -n 1 sensors
```
