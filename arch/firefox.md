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

Enter the following in the URL field:

```txt
about:config
```

---

## Open Tabs in Background

Middle clicking items in the bookmark while staying in current tab.

Search:

```txt
browser.tabs.loadBookmarksInBackground
```

Set it to `true`.

## Disable Fullscreen Notification

Turn off full screen notification.

Search:

```txt
full-screen-api.warning.timeout
```

Set it to `0`.

## Disable Menubar

Disable the `Alt` key from toggling the menubar.

Search:

```txt
ui.key.menuAccessKeyFocuses
```

Set it to `false`.

---

## Set to Default

Default browser in Hyprland.

```sh
# get current default browser
xdg-settings get default-web-browser

# set default browser to firefox
xdg-settings set default-web-browser firefox.desktop
```
