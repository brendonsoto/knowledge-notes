---
aliases: 
created: 2022-02-07, 11:51:56 am (Monday, February 7th)
updated: 2022-02-07, 11:52:53 am (Monday, February 7th)
---
Either run /sh on it on startup:
`docker run -it <img> /bin/sh` (or whatever shell)

If the container is *running already*:
`docker exec -it <container> /bin/sh`