# ImageMagick

Edit images with [ImageMagick](https://github.com/ImageMagick/ImageMagick).

## Table of Contents

- [Convert](#convert)
- [Rotate](#rotate)
- [Resize](#resize)
- [Quality](#quality)

---

## Convert

Changing file format.

```sh
magick input.jpg output.png
```

> [!NOTE]
> `convert` command has deprecated.

---

## Rotate

```sh
magick input.jpg -rotate 90 output.png
```

---

## Resize

Fit inside the frame with no distortion

```sh
magick input.png -resize 512x512 output.png
```

Overwrite original by using same name

```sh
magick input.png -resize 512x512 input.png
```

Force to exact size

```sh
magick input.png -resize 512x512 output.png
```

Resize only if larger then target

```sh
magick input.png -resize 512x512\> output.png
```

---

## Quality

Change image quality

```sh
magick input.png -quality 85 input.png
```
