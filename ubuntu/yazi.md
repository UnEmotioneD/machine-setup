# Yazi

Terminal file explorer written in rust.

## Reference

[yazi install debian](https://yazi-rs.github.io/docs/installation#debian)

## Table of Contents

- [Prerequisite](#prerequisite)
- [Build](#build)
- [Theme](#theme)
- [Update](#update)
- [Uninstall](#uninstall)

---

## Prerequisite

### Dependencies

```sh
sudo apt install ffmpeg 7zip jq poppler-utils fd-find ripgrep zoxide imagemagick build-essential
```

### Cargo

[Rust-lang tools install](https://rust-lang.org/tools/install/)

```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
rustup update
```

---

## Build

```sh
git clone https://github.com/sxyazi/yazi.git
cd yazi
cargo build --release --locked
```

move `yazi` and `ya` files to `$PATH`

```sh
sudo mv target/release/yazi target/release/ya /usr/local/bin/
```

---

## Theme

Add tokyonight theme with yazi package manager `ya`:

```sh
ya pkg add BennyOe/tokyo-night
```

This will create `flavors/` under yazi config directory,
you only need `flavors.toml` and `tmtheme.xml` files

Under the `~/.config/yazi` add `theme.toml` file, inside:

```toml
[flavor]
use = "tokyo-night"
# For Yazi 0.4 and above
dark = "tokyo-night"
```

---

## Update

1. pull latest update
2. update `cargo`
3. build with `cargo`
4. move `yazi` and `ya` to `$PATH`

---

## Uninstall

Remove the `yazi` and `ya` files under the `$PATH`

```sh
sudo rm /usr/local/bin/yazi /usr/local/bin/ya
```

Then remove the cloned repo
