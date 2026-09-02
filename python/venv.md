# Python Virtual Environment

## Table of Contents

- [Install PIP](#install-pip)
- [Create venv](#create-venv)
- [Activate](#activate)
- [Install Modules](#install-modules)
- [Freeze](#freeze)

---

## Install PIP

Python package manager:

```sh
sudo apt install python3-pip
```

---

## Create venv

Create at the desired location:

```sh
python3 -m venv <dir/venv-name>
```

---

## Activate

```sh
# `bash` and `zsh`
source ~/venv/bin/activate

# `fish`
source ~/venv/bin/activate.fish
```

### Deactivate

```sh
deactivate
```

---

## Install Modules

```sh
pip3 install numpy
```

### Update PIP

```sh
sudo pip3 install --upgrade pip
```

---

## Freeze

Save the environment exactly:

```sh
pip freeze > requirements.txt
```

Recreate the environment:

```sh
pip install -r requirements.txt
```

Refreeze after upgrades:

```sh
pip install --upgrade requests
pip freeze > requirements.txt
```
