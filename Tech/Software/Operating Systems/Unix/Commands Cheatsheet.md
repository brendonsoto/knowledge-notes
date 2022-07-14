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

## File related
### File system Overview
https://tldp.org/LDP/intro-linux/html/sect_03_01.html

### zip multiple files
`zip -r <output-name> <file1> <file2> ... <fileN>`

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