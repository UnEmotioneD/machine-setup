# CLI Tools

- Command Line Interface

## List of cli-tools

- git
- curl
- zoxide
- eza
- fzf
- bat
- tmux
- yazi
- stow
- lazygit
- flameshot: screen shot program
- fastfetch

---

## Bat

- File previewer

```bash
sudo apt install bat
```

- in `.bashrc` add alias to avoid collision

```bash
alias bat='batcat'
```

---

## Tmux Plugin Manager

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

---

## Fastfetch

- install with `PPA`

```bash
sudo add-apt-repository ppa:zhangsongcui3371/fastfetch
sudo apt upgrade
sudo apt install fastfetch
```

now you can run `fastfetch` from terminal

```bash
fastfetch
```

- uninstall

```bash
sudo apt remove fastfetch
sudo add-apt-repository --remove ppa:zhangsongcui3371/fastfetch
```
