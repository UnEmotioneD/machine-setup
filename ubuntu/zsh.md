# Z-Shell

Larger ecosystem and better customizability then BASH.

---

## Prerequisite

- git
- [curl](https://curl.se/): Data transfer by URL

```sh
sudo apt install git curl
```

---

## Install ZSH

```sh
sudo apt install zsh

# change default shell
chsh -s $(which zsh)
```

> [!NOTE]
> Restart for change to take effect.

---

## Install Oh My ZSH

- [Oh My ZSH](https://ohmyz.sh/#install): framework

```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

---

## Plugins

- [Powerlevel10k](https://github.com/romkatv/powerlevel10k?tab=readme-ov-file#manual): prompt theme
- [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions): fish like suggestions
- [fast syntax highlighting](https://github.com/zdharma-continuum/fast-syntax-highlighting): faster then zsh-syntax-highlighting

```sh
# powerlevel10k
git clone https://github.com/romkatv/powerlevel10k.git ~/.oh-my-zsh/custom/themes/powerlevel10k

# zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions

# fast syntax highlighting
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/fast-syntax-highlighting
```
