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

Execute the following command in the terminal:

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Add Homebrew to `PATH` (change the user name to yours):

```sh
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/unemotioned/.zprofile
&& eval "$(/opt/homebrew/bin/brew shellenv)"
```

Or copy it from the installation prompt.

Check if installed:

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

# update package index
brew update

# update outdated packages
brew upgrade

# remove orphaned packages
brew autoremove

# show orphaned packages before actually removing
brew autoremove --dry-run

# clear cache
brew cleanup

# check homebrew health
brew doctor
```

## Pin Package Version

Keep `brew upgrade` from updating the package:

```sh
brew pin openjdk@17
```

Show the pinned packages with the `--pinned` flag:

```sh
brew list --pinned
```

Or list outdated packages before `upgrade`:

```sh
brew outdated
```

### Unpin Package

```sh
brew unpin openjdk@17
```

---

## Save Installed Packages

Create a `Brewfile` where the command was executed:

```sh
brew bundle dump
```

To install with a `Brewfile`, run from the `Brewfile` file path:

```sh
brew bundle install
```
