# GPGME Error

Pacman could not find or process valid GPG because of the following possible reasons:

- corrupted pacman keyring
- corrupted package database
- problematic mirror

---

## Symptom

After running `sudo pacman -Syu` or similar commands:

```sh
...
error: GPGME error: No data
...
```

---

## 1. Back-up Mirrorlist

```sh
sudo mv /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.bak
```

## 2. Remove Stored Secrets

```sh
sudo rm -rf /etc/pacman.d/gnupg
sudo rm -R /var/lib/pacman/sync
```

## 3. Re-generate Keys

Initialize and re-generate the trust roots:

```sh
sudo pacman-key --init
sudo pacman-key --populate
```

## 4. Update Pacman

```sh
sudo pacman -Syyu
```
