# Vim

## Table of Contents

- [Vim Plug](#vim-plug)
- [Fugitive](#fugitive)

---

## Vim Plug

built-in plugin manager

### Install

install vim-plug at `~/.vim/autoload/plug.vim`

```sh
curl -fLo \
  ~/.vim/autoload/plug.vim --create-dirs \
  https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

### Usage

add it to `~/.vimrc`

```vim
call plug#begin('~/.vim/plugged')

" for example
Plug 'christoomey/vim-tmux-navigator'

call plug#end()
```

shout out the .`vimrc` and install it

```sh
:source ~/.vimrc # or :so
:PlugInstall
```

---

## Fugitive

```vim
:h fugitive

:h fugitive-maps
```

### Stage

open fugitive window

```vim
:G[it]
```

- `s`: stage
- `u`: unstage
- `-`: stage or unstage
- `U`: unstage all
- `X`: discard under cursor
- `=:` toggle inline diff

### Commit

```vim
:Gcommit
```

- `cc`: create commit
- `ca`: amend last commit
- `cs`: create squash! commit for the commit under the cursor

write commit and `:wq`

### Checkout

```vim
:Git checkout <branch-name>
```

- `co<Space>`: populate cmd with `:Git checkout`
- `cb<Space>`: populate cmd with `:Git branch`

### Pull

```vim
:G pull
```

### Rebase

```vim
:G rebase <branch-name>
```

- `r<Space>`: populate cmd with `:Git rebase`

### Merge

```vim
:G merge <branch-name>
```

### Push

```vim
:G push
```

---

### Blame

commit hash, author, date on split

```vim
:Git blame
```

### Conflict

```vim
:Gvdiff!
```

#### Diff Get

```vim
" accept from left (LOCAL)
:diffget //2

" accept from right (REMOTE)
:diffget //3
```

- `d2o`: accept local
- `d3o`: accept remote

#### Diff Put

from left or right window to push it to working tree buffer

```vim
:diffput <file-name>
```
