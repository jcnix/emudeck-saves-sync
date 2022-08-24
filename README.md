# emudeck-saves-sync

This script relies on [rclone](https://rclone.org), you will need to download it and copy the binary somewhere. I put mine in `~/Appications` which emudeck creates and installs emulator appimages to. If you change this, update `sync_saves.sh` to reflect that.

1. Copy `sync_saves.timer` and `sync_saves.service` to `~/.config/systemd/user`  
2. `sync_saves.sh` I have placed in a directory I created in `~/scripts`, but can be placed anywhere, you'll just need to update `sync_saves.service` to reflect that.  
3. You will need to update `sync_saves.sh` to point to your cloud provider configured with rclone as well.  The below command will guide you through the process.
```
~/Applications/rclone config
```


Start and enable the systemd timer.  
```
systemctl enable sync_saves.timer
systemctl start sync_saves.timer
```