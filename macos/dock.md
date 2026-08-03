# Dock

Quality of life improvements for macOS dock.

---

## Popout Speed

- Popout speed to 0 second delay
- Hide animation speed to 0.1 second
- Restart dock

```sh
defaults write com.apple.dock autohide-delay -int 0
defaults write com.apple.dock autohide-time-modifier -float 0.1
killall Dock
```

### Reset Popout Speed

Pass default values

```sh
defaults delete com.apple.dock autohide-delay
defaults delete com.apple.dock autohide-time-modifier
killall Dock
```

---

## Create Transparent Spacer

```sh
defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="small-spacer-tile";}'
killall Dock
```

---

## Reset Dock

Completely reset the dock.

```sh
defaults delete com.apple.dock
killall Dock
```
