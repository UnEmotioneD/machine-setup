# GitHub CLI

## Table of Contents

- [Install](#install)
- [Authenticate](#authenticate)
- [Clone](#clone)
- [Create Repository](#create-repository)

---

## Install

From AUR:

```sh
yay -S github-cli

# check installed
gh --version
```

---

## Authenticate

```sh
gh auth login
```

---

## Clone

```sh
gh repo clone <owner>/<repo>
```

From your repository without user name:

```sh
gh repo clone <repo>
```

---

## Create Repository

Create GitHub repository from local Git repository with at least one commit history.

```sh
gh repo create <repo-name> --source=. --public --push
```

- `--source=.`: current directory
- `--private` or `--public`
- `--push`: push local code immediately
