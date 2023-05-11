---
aliases: 
created: 2022-01-26, 2:22:27 pm (Wednesday, January 26th)
updated: 2022-01-26, 2:40:11 pm (Wednesday, January 26th)
---
What's a `Dockerfile`?
It's a file that provides steps for *building a Docker image.

- In your terminal, navigate to the directory with the `Dockerfile`
- Run `docker build -t <tag-name-for-you-to-reference-image-by> .`

You'll see a lot of text in the console.

Once the build process is completed you have a Docker image!
You can can *make a container to run the app* by using `docker run -dp <host-port>:<container-port>`
The `-d` flag is used to run the process in the background as a daemon.
The `p` flat is used to say "hey, bind the port on the computer in use to this port in the container."

## Related
- [[Tech/Docker/What is a Docker image?]]
- [[Tech/Docker/What is a Docker Container?]]