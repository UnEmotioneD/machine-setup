# Alacritty

Install the latest version of Alacritty on Ubuntu.

---

## Install

```sh
# add PPA
sudo add-apt-repository ppa:aslatter/ppa

# update APT
sudo apt update

# install
sudo apt install alacritty

# check installed
alacritty --version
```

---

## Uninstall

```sh
# remove alacritty package
sudo apt remove alacritty
sudo apt purge alacritty

# remove PPA
sudo add-apt-repository --remove ppa:aslatter/ppa
sudo apt update

# check uninstalled
which alacritty
```
