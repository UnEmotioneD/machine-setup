# Chromium

A web browser built for speed, simplicity and security.

> [!NOTE]
> You cannot even login to `Chromium`.

## Chromium VS Firefox

1. Chromium hides cursor automatically if needed when focus is changed to
   monkeytype or YouTube. While firefox won't.

2. Chromium renders image faster then firefox.

3. Chromium has better GitHub markdown inline code fonts. (Thicker then firefox)

> [!IMPORTANT]
> Swipe to go back history dose not work on `Chromium`.

## Table of Contents

- [Install](#install)
- [Settings](#settings)
- [Favorites](#favorites)
  - [Naver](#naver)
  - [YouTube](#youtube)
- [Extensions](#extensions)
  - [uBlock Origin](#ublock-origin)
  - [Unhook](#unhook)
  - [Vimium](#vimium)
  - [YouTube Auto HD + FPS](#youtube-auto-hd--fps)
  - [YouTube Auto Liker](#youtube-auto-liker)
- [Remove Firefox](#remove-firefox)

---

## Install

```sh
sudo pacman -S chromium
```

---

## Settings

- Appearance > Theme > `Dark`
- Show tab groups: `off`
- Show bookmarks bar: `on`
- Never translate Korean

---

## Favorites

### iCloud

### NAVER

- 설정
  - 화면 스타일
    - 다크 모드

### YouTube

- Settings
  - Playback and performance
    - Subtitles and Closed Captions: `off`
    - Browsing: Video previews: `off`

Ambient mode: `off`

### Claude

### GitHub

### Monkeytype

### Coupang

### Aliexpress

### Joongna

### Google Drive

### Google Photos

---

## Extensions

### uBlock Origin

### Material Icons for GitHub

### No CC: Hide YouTube Captions & Subtitles

### Unhook

- Hide Home Feed: `off`
- Hide Video Side bar: `off`
  - Hide Live Chat: `on`
  - Hide Fundraiser: `on`
- Hide Shorts: `on`
- Hide Comments: `on`
- Hide Mixes: `on`
- Hide Explore, Trending: `off`
- Disable Autoplay: `off`
- Disable Annotations: `off`

### Vimium

- Advanced Options
  - Scroll stop size: `1000px`
  - Use smooth scrolling: `off`
- Characters used for link hints
  - Ignore keyboard layout: `on` (to make it compatible with other input source
    then English on macOS)
- CSS for Vimium UI
  - Copy one of the theme to it [tokyonight.nvim - vimium](https://github.com/folke/tokyonight.nvim/tree/main/extras/vimium)

### YouTube Auto HD + FPS

- Extension is on: `on`
- Use the same quality for all frame rates: `on`
- Use enhanced bitrate when it's the highest quality: `on`
- Use super resolution when available: `on`
- Run on YouTube Music: `off`

### YouTube Auto Liker

- Enabled: `on`
- Subscribed Only: `on`
- Wait for Ads: `off`
- Delay (in seconds): `10`

---

## Remove Firefox

```sh
sudo pacman -Rns firefox

# No mercy!
rm -rf ~/.cache/mozilla
rm -rf ~/.config/mozilla
```
