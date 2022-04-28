---
aliases: 
created: 2022-04-28, 8:25:35 am (Thursday, April 28th)
updated: 2022-04-28, 8:28:42 am (Thursday, April 28th)
---
This is for if you install Ubuntu's [Snap](https://snapcraft.io/) app installer thing.

Removing it is a process, thankfully outlined [here](https://discuss.getsol.us/d/4840-removing-a-snapd-from-system).

Because I'm paranoid, here are the steps:

- Check list of installed snaps: `sudo snap list --all`
- Remove all of installed snaps: `sudo snap remove snapname` (for core snap also use a ``--revision revision_number option`)
- Remove a snapd by `sudo eopkg rmf snapd`
- List all /dev/loop devices currently mounted by snap: `sudo mount | grep snap | awk '{print $3}'``
- Unmount this devices by `sudo umount device_name`
- Remove snap directory: `sudo rm -rf /var/lib/snap && sudo rm -rf /snap`
- Remove all files that used to mount a snap packages from /var/lib/snapd/snaps to /snapon the boot:
    ```
    sudo find /etc/systemd/system -name "snap-*.mount" -delete
    sudo find /etc/systemd/system -name "snap.*.service" -delete
    sudo find /etc/systemd/system/multi-user.target.wants -name "snap-*.mount" -delete
    sudo find /etc/systemd/system/multi-user.target.wants -name "snap.*.service" -delete
    ```
- Reboot, and that's all. snapd is removed. You're perfect.