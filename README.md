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

## Install and configure k3s

TODO

## Configure reliable storage

TODO: MD + XFS + LUKS

## Configure S3 backups

TODO: rclone

## Tiered backups

TODO: RAM --> SSD --> HDD --> S3

## Configure wi-fi access point

TODO: hostapd

## Configure local DNS server and root CA

TODO

## Running pihole in k8s

TODO

## Using Alpine in diskless mode

TODO: Explain lbu + crash tests
