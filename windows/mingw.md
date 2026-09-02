# Minimalist GNU for Windows

Install `g++` and `mingw32-make` to build and run C++ projects.

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

From the `MSYS2 UCRT64` terminal:

```sh
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

`toolchain` includes the following packages: [packages.msys2.org](https://packages.msys2.org/groups/mingw-w64-ucrt-x86_64-toolchain)

Check installations:

```sh
gcc --version # c compiler
g++ --version # cpp compiler
mingw32-make --version # make for windows
```

---

## Add to PATH

Add the following directory to the `Path` of the **system environment variable**.

```sh
C:\msys64\ucrt64\bin
```

---

## Build

Build with the `make` command using a `Makefile`.

### Makefile

Inside `Makefile`, change the following commands from `bash`:

```Makefile
@mkdir -p $(BUILD_DIR)

@rm -rf $(BUILD_DIR)
```

to **powershell**:

```Makefile
@if not exist $(BUILD_DIR) mkdir $(BUILD_DIR)

@if exist $(BUILD_DIR) rmdir /S /Q $(BUILD_DIR)
```

> [!IMPORTANT]
> Must use **tabs** for indent in a `Makefile`.

### BASH (MSYS2)

**Optionally** use the MSYS `bash` terminal by default for the current project in VSCode.

1. From the command palette, search `Select Default Profile` and choose `bash (MSYS2)`.
2. Move `terminal.integrated.profiles.windows` and `terminal.integrated.defaultProfile.windows`
   from user settings to `.vscode/settings.json` to make it project-specific.
3. Install packages to use on the `bash` terminal:

```sh
pacman -Syu gcc make
```

Now you can use it as same as from unix system.
