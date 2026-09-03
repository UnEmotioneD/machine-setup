# Advanced Package Tool

Package manager for debian based linux distributions.

## Table of Contents

- [General Usage](#general-usage)
  - [Flags](#flags)
- [Cleanup](#cleanup)
- [Pin Version](#pin-version)
- [Fix Package](#fix-package)

---

## General Usage

- Update local package index:

```sh
sudo apt update
```

- Upgrade packages:

```sh
# list outdated packages
apt list --upgradeable

# upgrade outdated packages
sudo apt upgrade <pkg-name>
```

- Search:

```sh
apt search <pkg-name>

# search from cache for faster search
apt-cache search . | fzf

# search from installed packages
sudo apt list --installed | fzf
```

- Install:

```sh
sudo apt install <pkg-name>
```

- Remove:

```sh
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

## Cleanup

- Remove unused dependencies:

```sh
sudo apt autoremove
```

- Clear download cache:

```sh
sudo apt clean
```

---

## Pin Version

Keep package from being upgraded.

```sh
sudo apt-mark hold <pkg-name>
```

- Undo hold:

```sh
sudo apt-mark unhold <pkg-name>
```

- List held packages:

```sh
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
