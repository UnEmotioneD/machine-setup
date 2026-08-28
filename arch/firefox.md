# Firefox

Configure advanced settings.

## Table of Contents

- [Advanced Settings](#advanced-settings)
- [Open Tabs in Background](#open-tabs-in-background)
- [Disable Fullscreen Notification](#disable-fullscreen-notification)
- [Disable Menubar](#disable-menubar)
- [Set to Default](#set-to-default)

---

## Advanced Settings

Enter the following in URL field.

```sh
about:config
```

---

## Open Tabs in Background

Middle clicking items in the book mark while staying in current tab.

1. Search `browser.tabs.loadBookmarksInBackground`
2. set it to `true`

## Disable Fullscreen Notification

Turn off full screen notification.

1. Search `full-screen-api.warning.timeout`
2. set it to `0`

## Disable Menubar

Disable `Alt` key from toggling menubar.

1. Search `ui.key.menuAccessKeyFocuses`
2. Set it to `false`

---

## Set to Default

Default browser in hyprland.

```sh
# get current default browser
xdg-settings get default-web-browser

# set default browser to firefox
xdg-settings set default-web-browser firefox.desktop
```
