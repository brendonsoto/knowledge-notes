---
aliases: 
created: 2022-01-26, 2:36:43 pm (Wednesday, January 26th)
updated: 2022-01-26, 2:39:30 pm (Wednesday, January 26th)
---
A Docker Container is a virtualized run-time environment for an application.
In other words, a container is an isolated area for an application to run in.

It's created from a [[Tech/Docker/What is a Docker image?|Docker image]].

---
A container is essentially a combo of:
- chroot
- namespaces
- cgroups

The chroot piece is used to establish a new "root". The directory of this new root will need functionality from `/bin` which can be done by copying the binaries from the parent system to the sub system (e.g. `cp -R /bin /my-root` -- don't actually do this. just take what you need.).

Namespaces are a part of isolating containers from each other. Without them, there's nothing stopping one user from seeing what another one is doing. Hosts can see what child processes are doing but child processes can't see what's going on in the Host.

Cgroups are for setting up constraints per namespace. These constraints can be attributes like CPU percentage, storage size, RAM, etc. This tech comes from Google. The idea behind it was to prevent one program from eating up the resources of others.

## Resources
- https://phoenixnap.com/kb/docker-image-vs-container
- https://frontendmasters.com/courses/complete-intro-containers/

## Related
- [[Tech/Docker/How To/Work with a Dockerfile]]
- [[Tech/Docker/What is a Docker image?]]