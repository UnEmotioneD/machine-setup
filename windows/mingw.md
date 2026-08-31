# Minimalist GNU for Windows

install g++ and mingw32-make to build and run cpp projects

## Reference

- [VSCode - GCC on Windows](https://code.visualstudio.com/docs/cpp/config-mingw)

## Table of Contents

- [Install](#install)
- [Add to PATH](#add-to-path)
- [Build](#build)
  - [Powershell](#powershell)
  - [BASH (MSYS2)](#bash-msys2)

---

## Install

download and install [MSYS2](https://www.msys2.org/)

### Toolchain

from `MSYS2 UCRT64` terminal

```sh
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

`toolchain` includes the following packages: [packages.msys2.org](https://packages.msys2.org/groups/mingw-w64-ucrt-x86_64-toolchain)

check installations:

```sh
gcc --version # c compiler
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

build with `make` command using `Makefile`

### Powershell

inside `Makefile` change following commands from:

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
