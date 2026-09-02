# Autostart

Stop programs from starting automatically.

---

Check if the program is under the `autostart` directory.

`nm-applet` for example:

```sh
ls /etc/xdg/autostart | grep nm-applet
```

Add `Hidden=true` to the `nm-applet.desktop` file:

```sh
sudo sh -c 'echo "Hidden=true" >> /etc/xdg/autostart/nm-applet.desktop'
```
