# [Alacritty](https://github.com/alacritty/alacritty)

A fast, cross-platform, [OpenGL](https://www.opengl.org/) terminal emulator.

---

## Install

Install latest version by adding PPA (Personal Package Archive).

```sh
# add PPA
sudo add-apt-repository ppa:aslatter/ppa

sudo apt update

# install
sudo apt install alacritty

# confirm installation
alacritty --version
```

---

## Uninstall

```sh
# remove package and config
sudo apt purge alacritty

# remove PPA
sudo add-apt-repository --remove ppa:aslatter/ppa

sudo apt update

# confirm uninstallation
which alacritty
```
