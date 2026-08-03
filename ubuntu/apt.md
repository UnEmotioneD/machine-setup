# Advanced Package Tool

## Table of Content

- [Before Use](#before-use)
- [How to Use](#how-to-use)
- [Search](#search)
- [Cleanup](#cleanup)
- [Flags](#flags)
- [Fix Install](#fix-install)

---

## Before Use

- `sudo`: Super User Do
  - install, remove, update
  - modifying sys files(/etc, /usr, /bin, ...)
  - managing services
  - changing user

```sh
# update apt
sudo apt update

# check outdated package
apt list --upgradeable

# upgrade outdated pkg
sudo apt upgrade

# keep package from being upgraded
sudo apt-mark hold openjdk-17-jdk

# undo hold
sudo apt-mark unhold openjdk-17-jdk
```

---

## How To Use

You can pass more then one argument

```sh
sudo apt install {pkg} {pkg} ...
```

---

## Search

```sh
# update apt local cache
apt update

# pipe installed package list to fzf
apt-cache search . | fzf

# list installed packages
apt list --installed
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

## Flags

`--yes` or `-y`: automatic yes

`--quiet` or `-q`: quieter output

`--no-install-recommends` or `--no-install-reco`

`--reinstall`

`--purge`

---

## Fix Install

### Fix Broken Dependencies

```sh
sudo apt install -f
```

### Check not being upgraded

```sh
sudo apt dist-upgrade -a
```

You may install the package separated

### Run Final Upgrade

```sh
sudo apt full-upgrade -y
```
