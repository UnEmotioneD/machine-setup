# [Brillo](https://gitlab.com/cameronnemo/brillo)

Human eye friendly brightness control by changing brightness exponentially.

## Reference

- [You're Probably Doing Screen Brightness in Arch Linux Wrong - Eric Murphy](https://www.youtube.com/watch?v=pGOaSS8nEQA)

---

## Installation

### 1. Dependency

```sh
sudo pacman -S go-md2man
```

### 2. Build

```sh
git clone https://gitlab.com/cameronnemo/brillo.git
cd brillo
make
```

### 3. Install

with `setgid` every users can use without extra permissions

```sh
sudo make install.setgid
```

and reboot

---

## Usage

inside `~/.config/hypr/hyprland.conf` replace the `brightnessctl s 10%+` with `brillo`:

```sh
brillo -q -u 1000 -A 5  # brightness up
brillo -q -u 1000 -U 5  # brightness down
```

- `-q` : change brightness experientially
- `-u` : fade animation 1000ms (0.1sec)
- `-A` : brightness up
- `-U` : brightness down
