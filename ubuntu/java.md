# Java

How to change java version when you have multiple JDKs installed.

---

## Package Names

- Pacman
  - `jdk17-openjdk`
  - `jdk21-openjdk`

- APT
  - `openjdk-17-jdk`
  - `openjdk-21-jdk`

---

## Check Installed

- Arch

```sh
archlinux-java status
```

- Ubuntu

```sh
sudo apt list --installed | grep openjdk
```

---

## Change Version

- Arch

```sh
sudo archlinux-java set java-17-openjdk
```

- Ubuntu

```sh
sudo update-alternatives --config java

# java compiler separately
sudo update-alternatives --config javac
```

Confirm version change:

```sh
java --version
```
