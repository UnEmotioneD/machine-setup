# Minimalist GNU for Windows

install g++ and mingw32-make to build and run cpp projects

## Table of Contents

- [Install MSYS2](#install-msys2)
- [Install gcc, make](install-gcc-make)
- [Add to PATH](#add-to-path)
- [Build](#build)
  - [Powershell](#powershell)
  - [BASH (MSYS2)](#bash-msys2)

---

## Install [MSYS2](https://www.msys2.org/)

download and install

---

## Install gcc, make

from `MSYS2 UCRT64` terminal

```sh
pacman -S mingw-w64-ucrt-x86_64-gcc mingw-w64-ucrt-x86_64-make
```

check installations:

```sh
g++ --version # cpp compiler
mingw32-make --version # make for windows
```

---

## Add to PATH

add the following directory to path of system environment variable

```sh
C:\msys64\ucrt64\bin
```

---

## Build

### Powershell

change following commands from:

```Makefile
@mkdir -p $(BUILD_DIR)

@rm -rf $(BUILD_DIR)
```

to these:

```Makefile
@if not exists $(BUILD_DIR) mkdir $(BUILD_DIR)

@if exist $(BUILD_DIR) rmdir /S /Q $(BUILD_DIR)
```

> [!IMPORTANT]
> Must use **TAB** for indentations.

### BASH (MSYS2)

from **Select Default Profile** choose `bash (MSYS2)`

install package to use on bash terminal:

```sh
pacman -Syu gcc make
```

you can use it as same as from unix system
