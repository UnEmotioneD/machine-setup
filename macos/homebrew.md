# [Homebrew](https://brew.sh/)

Package manager for macOS.

## Table of Contents

- [Install](#install)
- [Usage](#usage)
- [Pin Package Version](#pin-package-version)
  - [Unpin Package](#unpin-package)
- [Save Installed Packages](#save-installed-packages)

---

## Install

execute following command in terminal

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

add homebrew to path (change the user name to yours)

```sh
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/unemotioned/.zprofile
&& eval "$(/opt/homebrew/bin/brew shellenv)"
```

or copy it from the installation prompt

check if installed

```sh
brew --version
```

---

## Usage

```sh
# search
brew search {pkg}

# list installed
brew list
brew list | grep {pkg}

# install package
brew install {pkg}

# remove packages
brew uninstall {pkg}

# update homebrew itself
brew update

# update outdated packages
brew upgrade

# remove orphaned packages
brew autoremove

# show orphaned packages before actually removing
brew autoremove --dry-run

# clear cache
brew clean

# check homebrew health
brew doctor
```

## Pin Package Version

keep the `brew upgrade` from updating the package

```sh
brew pin openjdk@17
```

show the pinned packages with `--pinned` flag

```sh
brew list --pinned
```

or list outdated packages before `upgrade`

```sh
brew outdated
```

### Unpin Package

```sh
brew unpin openjdk@17
```

---

## Save Installed Packages

create `Brewfile` where the cmd was executed

```sh
brew bundle dump
```

to install with `Brewfile`, run from `Brewfile` file path

```sh
brew bundle install
```
