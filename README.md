# Alpine scripts

## Mounting a bitlocker disk

```bash
# Install dislocker from edge/testing repo. Reboot is required to pick up the driver.
apk update
apk add dislocker --repository=http://dl-cdn.alpinelinux.org/alpine/edge/testing/
reboot now

mkdir -p /media/bitlocker
mkdir -p /media/bitlockermount

# Find the right device and mount it using dislocker
fdisk -l
dislocker /dev/sdc2 -u -- /media/bitlocker

# Mount the dislocker loop device
losetup -f /media/bitlocker/dislocker-file
mount -t ntfs /dev/loop0 /media/bitlockermount
```
