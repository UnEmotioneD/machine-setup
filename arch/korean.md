# Korean Localization on Arch Linux (Hyprland)

This guide covers the setup of Korean fonts and input methods on Arch Linux with Hyprland.

---

## 1. Install Korean Fonts

To ensure proper font rendering, install the following packages:

```sh
sudo pacman -S adobe-source-han-sans-kr-fonts adobe-source-han-serif-kr-fonts
```

---

## 2. Install Fcitx5 Input Method

Fcitx5 is a modern input method framework supporting Hangul (Korean).

```sh
yay -S fcitx5-im fcitx5-hangul fcitx5-configtool
```

---

## 3. Configure Environment Variables

Add the following lines to `~/.profile` and ensure `.bashrc` sources it:

```sh
export GLFW_IM_MODULE=fcitx # Needed for some Wayland applications
export GTK_IM_MODULE=wayland
export QT_IM_MODULE=fcitx
export SDL_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
```

To apply the changes immediately, run:

```sh
source ~/.profile
```

---

## 4. Autostart Fcitx5 in Hyprland

Add the following line to your `~/.config/hypr/hyprland.conf` to start Fcitx5 automatically:

```ini
exec-once = fcitx5 -d
```

---

## 5. Configure Fcitx5

Launch `fcitx5-configtool`.

### Input Method Tab

- Add `Hangul` to the **Current Input Method** list.

### Global Options Tab

- Set `Trigger Input Method` to **Right Alt (R_Alt)**
- Disable `Show Input Method Information when switch input method`

![fcitx-config-global-options](../assets/fcitx-config-global-options.png)
