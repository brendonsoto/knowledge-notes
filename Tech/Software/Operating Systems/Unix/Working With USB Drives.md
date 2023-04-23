---
tags: linux unix usb cli
created: Sunday, April 23, 2023 2:35 PM
created_at: 2023-04-23T14:35:33-04:00
---
## Clearing a USB drive
### Using `dd`
[Source](https://www.makeuseof.com/securely-erase-usb-drive-sd-card-linux/)

- [find the USB drive](#Finding%20a%20connected%20USB%20drive) 
- `sudo umount /dev/sd*`
    - Note: the asterisk in `sd*` is a placeholder. More concrete example: `sudo umount /dev/sdb`
- `sudo dd if=/dev/zero of=/dev/sd* bs=4096 status=progress`

### Using `shred`
[Source](https://www.makeuseof.com/securely-erase-usb-drive-sd-card-linux/)

- [find the USB drive](#Finding%20a%20connected%20USB%20drive) 
- `sudo shred -vz /dev/sd*`
    - `-v` = verbose
    - `-z` = does another pass where the data is overwritten with zeroes

## Finding a connected USB drive
`$ lsblk`

From the man page:
> lsblk - list block devices

<details>
    <summary>What is a block device?</summary>
    From the [IEEE](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap03.html#tag_03_79):
    > A file that refers to a device. A block special file is normally distinguished from a character special file by providing access to the device in a manner such that the hardware characteristics of the device are not visible.
</details>

This will give you output similar to:
```
NAME                                          MAJ:MIN RM   SIZE RO TYPE  MOUNTPOINTS
sda                                             8:0    0 238.5G  0 disk
├─sda1                                          8:1    0   600M  0 part  /boot/efi
├─sda2                                          8:2    0     1G  0 part  /boot
└─sda3                                          8:3    0 236.9G  0 part
  └─luks-12c30c53-2da4-460d-8f56-e4a87e4084dd 253:0    0 236.9G  0 crypt /home
                                                                         /
sdb                                             8:16   1  14.3G  0 disk
zram0                                         252:0    0   7.6G  0 disk  [SWAP]
```

Here `sda` represents my computer's hard drive. I had just [cleared my USB drive](#Clearing%20a%20USB%20drive) so `sdb` doesn't have any subsections to it.


## Putting an OS on a USB drive
1. Find the USB drive partition name using either:
    - `lsblk`
    - `sudo fdisk -l`
2. Unmount the mounted partition:
    - `umount /dev/sd*` (e.g.  if the partition was mounted at `/dev/sdb` you'd run `umount /dev/sdb`)
3. Write to the drive:
    - `dd if=/path/to/image.iso of=/dev/sd* bs=8M status=progress oflag=direct`