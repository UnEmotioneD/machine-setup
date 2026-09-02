# Package

Packages to install for general Ubuntu usage.

---

## Recommended Packages

- `build-essential`: tools and libs for building software from source
- `curl`: data transfer by URL
- `eza`: better `ls`
- `git-delta`: git diff tool
- `git`: version control system
- `stow`: symlink manager
- `tree`: directory previewer
- `zoxide`: better `cd`

```sh
sudo apt install build-essential curl git git-delta tree eza zoxide
```

---

## Deb Packages

- Google Chrome
- Visual Studio Code

Download files with `.deb`, which is for Debian/Ubuntu.

`cd` into the downloads directory from the terminal:

```sh
cd Downloads/
```

Install with the `dpkg` (Debian package) command:

```sh
sudo dpkg -i <deb-file>
```

You can pass multiple file names as arguments to the `dpkg` command.

- To run an `.ipynb` file from VSCode, install `pip3` and `ipykernel`.
  - `ipykernel`: to run locally from VSCode
  - `jupyter`: to run from a venv

```sh
sudo apt install python3-pip python3-ipykernel
```
