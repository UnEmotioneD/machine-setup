# SCP

Move files between SSH machines

from remote do `pwd` and use that output

```sh
scp -r ./myfolder user@remote:/path/to/destination/
# example
scp -r ~/pinky_lcd pinky@192.168.4.1:/home/pinky/
```
