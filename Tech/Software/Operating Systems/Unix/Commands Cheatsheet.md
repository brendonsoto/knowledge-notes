---
aliases: 
created: 2022-01-18, 4:52:57 pm (Tuesday, January 18th)
updated: 2022-04-29, 8:47:25 am (Friday, April 29th)
---
One of the few files where I'm breaking my rule of making separate files to break down potentially verbose concepts.

## Architecture related
### Find the architecture of your computer
`uname -m`

### Find the processor info
`cat /proc/cpuinfo`

---

## File related
### Extract `*.tar.xz` files
`tar -xf <file>`
For verbose, add `-v` flag

If the file is also gzipped, use `-z`

### File system Overview
https://tldp.org/LDP/intro-linux/html/sect_03_01.html

### sha256 and checksums
You may see something regarding *Sha256* when downloading a file.
For example, there's a column for it on [Zig's downloads page](https://ziglang.org/download/).
This is to make sure the file is legit once downloading it.

Once you have downloaded the file, run `sha256sum <file>` and compare its output with what the source says the result should be.
A better way would be to copy the checksum from the downloads page and save it to a file alongside the name of the file.
The name and checksum should be separated by two spaces: `<hash>  <file-name>`.
Once you have that, you can run `sha256 --check <file-with-checksum-and-downloaded-file-name>`

### zip multiple files
`zip -r <output-name> <file1> <file2> ... <fileN>`

---

## Process related
### Find the PID of a server still running on a port
`lsof -i :8080`

## Reference multiple directories with the same parent
Consider the following directory structure:
```
lib/
- assets/
- tests/
- utils/
- ... # more directories
```

To delete multiple directories, use **brackets** in the parent directory:
`rm lib/{assets,tests,utils}`

## Save the output of a command to a file
For both stdin and stderr:
`cmd &> file`

## Variables
From `$1` to `$@` and talking about `shift`:
https://www.shellscript.sh/variables2.html

---

## Putting an OS on a USB drive
1. Find the USB drive partition name using either:
    - `lsblk`
    - `sudo fdisk -l`
2. Unmount the mounted partition:
    - `umount /dev/sd*` (e.g.  if the partition was mounted at `/dev/sdb` you'd run `umount /dev/sdb`)
3. Write to the drive:
    - `dd if=/path/to/image.iso of=/dev/sd* bs=8M status=progress oflag=direct`