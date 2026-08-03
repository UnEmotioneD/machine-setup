# Secure Shell

`SSH` keys provide a secure and convenient way to authenticate with remote
servers and services like **GitHub**.

## Table of Contents

- [1. Generate Key](#1-generate-key)
- [2. Start Agent](#2-start-agent)
- [3. Configure SSH to Use the Key](#3-configure-ssh-to-use-the-key)
- [4. Add Key to Agent](#4-add-key-to-agent)
- [5. Copy Public Key](#5-copy-public-key)
- [6. Test Connection](#6-test-connection)

---

## 1. Generate Key

Generate using `ED25519` algorithm (recommended for security and performance):

```sh
ssh-keygen -t ed25519 -C "<your@email.com>"
```

When prompted:

- **Enter a file location:** Press **Enter** to use the default path (`~/.ssh/id_ed25519`).
- **Enter a passphrase (optional):** can be empty

---

## 2. Start Agent

SSH agent keeps your key unlocked while you work, so you don’t need to enter the passphrase every time.

```sh
eval "$(ssh-agent -s)"
```

---

## 3. Configure SSH to Use the Key

Create `~/.ssh/config` file and add following content:

```config
Host *
    AddKeysToAgent yes
    IdentityFile ~/.ssh/id_ed25519
```

This configuration ensures:

- Your SSH key is automatically added to the agent.
- The correct key (`~/.ssh/id_ed25519`) is used by default.

---

## 4. Add Key to Agent

To ensure your SSH key is loaded, run:

```sh
ssh-add ~/.ssh/id_ed25519
```

---

## 5. Copy Public Key

Print public key with `cat` or `bat (Debian/Ubuntu: batcat)`:

```sh
bat ~/.ssh/id_ed25519.pub
```

Copy the output and add it to your GitHub account:
[GitHub SSH Key Settings](https://github.com/settings/keys)

**New SSH Key** > Paste the copied key

> [!IMPORTANT]
> Make sure there is no trailing spaces.

---

## 6. Test Connection

```sh
ssh -T git@github.com
```

**_Type_** `yes`.

Output should be:

```text
Hi {user-name}! You've successfully ...
```
