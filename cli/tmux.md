# [TMUX](https://github.com/tmux/tmux)

Build tmux locally from archive file.

---

## Prerequisite

```sh
brew install pkgconf libevent ncurses autoconf
```

---

## Download

download `tar.gz` from [github release](https://github.com/tmux/tmux/releases)

---

## Unzip Archive

go to directory where the `tmux-x.x.tar.gz` is at unzip and move into it

- `-x`: extract files from the archive
- `-z`: decompress using gzip for .gz files
- `-f`: specifies the file to operate on (next args is the archive name)

```sh
tar -zxf tmux-3.6b.tar.gz
cd tmux-3.6b
```

---

## Install

```sh
./configure CPPFLAGS="-I/opt/homebrew/include" LDFLAGS="-L/opt/homebrew/lib" --enable-utf8proc
make && sudo make install
```

you can remove the archive and unzipped files after this

---

## Uninstall

if you do `sudo make uninstall` at the unzipped archive directory it will prompt
to do the following

```sh
sudo rm /usr/local/bin/tmux
```
