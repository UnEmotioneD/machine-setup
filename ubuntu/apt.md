# Advanced Package Tool

package manager for debian based linux distros

## Table of Contents

- [General Usage](#general-usage)
  - [Flags](#flags)
- [Search](#search)
- [Cleanup](#cleanup)
- [Pin Version](#pin-version)
- [Fix Package](#fix-package)

---

## General Usage

```sh
# update local package index
sudo apt update <pkg-name>

# list outdated packages
apt list --upgradeable

# upgrade outdated packages
sudo apt upgrade <pkg-name>

# search packages from database
apt search <pkg-name>

sudo apt install <pkg-name>

sudo apt remove <pkg-name>

# also removes package managed configuration files
sudo apt purge <pkg-name>
```

> [!TIP]
> You can pass multiple arguments to commands such as `install` and `remove`.

### Flags

- `--yes` / `-y`: automatic yes to prompts
- `--quiet` / `-q`: quieter output
- `--no-install-recommends` / `--no-install-reco`
- `--reinstall`

---

## Search

```sh
sudo apt update

# search from cache for faster search
apt-cache search . | fzf

# search from installed packages
sudo apt list --installed | fzf
```

---

## Cleanup

```sh
# remove unused dependencies
sudo apt autoremove

# clear download cache
sudo apt clean
```

---

## Pin Version

keep package from being upgraded

```sh
sudo apt-mark hold <pkg-name>

# undo
sudo apt-mark unhold <pkg-name>

# list held packages
apt-mark showhold
```

---

## Fix Package

```sh
# fix broken dependencies
sudo apt install -f

# install or remove packages when necessary
sudo apt full-upgrade -y
```
