# SCP

Move files between local and SSH machine.

- Copy directory with `recursive` flag.

```sh
scp -r ./myfolder user@ip_addr:/path/to/destination/

# example
scp -r ~/pinky_lcd pinky@192.168.4.1:/home/pinky/
```
