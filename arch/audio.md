# Audio

Setup [PipeWire](https://pipewire.org/) audio stack.

---

## Install

- `pipewire-audio`: PipeWire audio stack
  - `pipewire`: core audio server
  - `pipewire-pulse`: PulseAudio compatibility
  - `wireplumber`: audio session manager
- `pavucontrol`: audio control GUI
- `bolt`: Thunderbolt device manager

```sh
sudo pacman -S pipewire-audio pavucontrol bolt
```

---

## Enable Services

```sh
systemctl --user enable --now pipewire pipewire-pulse wireplumber
```
