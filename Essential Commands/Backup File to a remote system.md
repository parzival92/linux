# Backup files to a Remote System

- Syncing Two Directories(rysnc)
```
rsync -a Pictures/ username@hostname:/home/user/Pictures
```
- Disk Imaging
```
sudo dd if=/dev/vda/ of=diskimage.raw bs=1M status=progress
# For Restore
replace of and if
```


