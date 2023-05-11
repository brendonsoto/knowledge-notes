---
aliases: 
created: 2022-08-12, 1:39:32 pm (Friday, August 12th)
updated: 2022-08-12, 1:49:14 pm (Friday, August 12th)
---
*Bare metal* (meaning running your own computers/servers) was one way people would use to deploy sites. It was thought as more secure since you're not sharing resources with others. If you had a good hardware supplier it was cheaper than other options. You can tweak it to your hearts content. This route could be more expensive both on the hardware and from the people/maintainability side as you would have to worry about physical factors and the occasional spikes in traffic.

*Virtual machines* are another alternative. It's a server w/ multiple operating systems running on it. There's always the possibility of leaking sensitive information across the users of the machine. A malicious user could also take down the entire machine by running a program that would intentionally hog resources (a fork bomb). There still are reasons to use VMs (not discussed yet).

There's the *public cloud* which comprises services like AWS, Azure, and Google Cloud. Maintenance is removed at an added cost, but is generally cheaper for people who don't know or want to manage the machine. You still have to manage the OS though.

*Containers* were seen as "lightweight" compared to bare metal or VMs since a container was essentially a snapshot of a file system that can be given to a platform to reproduce the environment. You can have multiple containers running side by side on the same server but there are better security measures to protect against leaking data.