# fprintd

How to register finger prints on Linux with `fprintd`.

---

## Install

```sh
sudo pacman -S fprintd libfprint
```

---

## Enable

```sh
sudo systemctl enable --now fprintd
```

---

## Enroll

- Available fingers:
  - `left-little-finger`
  - `left-ring-finger`
  - `left-middle-finger`
  - `left-index-finger`
  - `left-thumb`

  - `right-thumb`
  - `right-index-finger`
  - `right-middle-finger`
  - `right-ring-finger`
  - `right-little-finger`

```sh
sudo fprintd-enroll -f right-index-finger
```

---

## Verify

```sh
sudo fprintd-verify -f right-index-finger
```

---

## Troubleshooting

### enroll-duplicate

Delete if fingerprint is already stored:

```sh
sudo fprintd-delete $USER
# or
sudo fprintd-delete root
```
