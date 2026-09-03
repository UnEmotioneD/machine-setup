# [Fastfetch](https://github.com/fastfetch-cli/fastfetch)

System information fetch program.

---

## Install

Install latest version by adding PPA (Personal Package Archive).

```sh
# add PPA
sudo add-apt-repository ppa:zhangsongcui3371/fastfetch

sudo apt update

# install
sudo apt install fastfetch

# confirm installation
fastfetch --version
```

---

## Uninstall

```sh
# remove package and config
sudo apt purge fastfetch

# remove PPA
sudo add-apt-repository --remove ppa:zhangsongcui3371/fastfetch

sudo apt update

# confirm uninstallation
which fastfetch
```
