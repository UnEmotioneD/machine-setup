# Minimalist GNU for Windows

install g++ and mingw32-make to build and run cpp projects

## Reference

- [VSCode - GCC on Windows](https://code.visualstudio.com/docs/cpp/config-mingw)

## Table of Contents

- [Install](#install)
- [Add to PATH](#add-to-path)
- [Build](#build)
  - [Makefile](#makefile)
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

Add the following directory to the `Path` of **system environment variable**.

```sh
C:\msys64\ucrt64\bin
```

---

## Build

build with `make` command using `Makefile`

### MakeFile

inside `Makefile` change following commands from **BASH**:

```Makefile
@mkdir -p $(BUILD_DIR)

@rm -rf $(BUILD_DIR)
```

to **powershell**:

```Makefile
@if not exists $(BUILD_DIR) mkdir $(BUILD_DIR)

@if exist $(BUILD_DIR) rmdir /S /Q $(BUILD_DIR)
```

> [!IMPORTANT]
> Must use **Tabs** for indent in `makefile`.

### BASH (MSYS2)

**_Optionally_** to use msys bash terminal by default for current project on vscode.

1. From command prompt search **Select Default Profile** and choose `bash (MSYS2)`.
2. Move settings `terminal.integrated.profiles.windows` and `terminal.integrated.defaultProfiles.windows`
   from user settings to **.vscode/settings.json** to make it project specific.
3. Install package to use on bash terminal:

```sh
pacman -Syu gcc make
```

Now you can use it as same as from unix system.
