---
aliases: 
tags:
  - docker
  - infra
created: Monday, October 2, 2023 10:11 AM
created_at: 2023-10-02T10:11:14-04:00
updated: 2023-10-03, 4:26:26 pm (Tuesday, October 3rd)
---
# Everything Docker

## Questions

### What's a decent maintenance routine?

How do you know when volumes are unused? or containers?

## Commands

In general, the docker CLI is _really_ helpful at finding info through `docker help` or `docker <command> help`. If you can't find something more specific here (e.g. naming containers) it's probably because it's easy to find via `docker help`.

### build

Example: `docker build .`

Creates an [image](#Image) based off of a given [Dockerfile](#Dockerfile).
To make the resulting image easier to find, use `-t name` (think "tag" the image with this name).

### compose

This probably deserves its own section but this command works with a `compose.yml` file to manage setting up multiple docker containers. A [network](#Network) is automatically created as well as a group for the containers. Both derive their name from the directory the `compose.yml` file is in.

### network

Example: `docker network create <name>`

### volume

Example: `docker volume create <my-vol>`

## Glossary

### Bind mount

A bind mount takes a path on the host machine and allows a container to access it.

When are bind mounts useful? When you want your application to respond to changes to files, like locally developing an application.

Related: [volume](#volume)

### Container

A container is an isolated running process based off of an [Image](#Image).

### Dockerfile

A file that describes how to build an [image](#Image).

### Image

An image is a filesystem that contains everything to run an application (binaries, scripts, dependencies, etc.).

### Network

A network can be used to enable communication between containers.

When is a network useful? For [enabling multiple containers to talk to each other](#Have%20multiple%20containers%20talk%20to%20each%20other).

### Volume

A volume is a way to save data created from a container to the host machine. It's like a directory on the host machine's computer that can be used in place of a path inside the container. A container can then be created using a volume as a mount so anything that's created in the mount's path is saved to the host machine's file system. Docker manages where a volume is created.

When are volumes useful? When you need to persist data.

Related: [Bind mount](#Bind%20mount)

## How to

### Have multiple containers talk to each other

First, you have to establish a [network](#Network). To then connect a container to that network provide the `--network <network-name>` option to `docker run`.

To make containers _easier to find on the network_ you can use the `--network-alias <alias>` option when running `docker run`. This will enable you to refer to other containers on the network by an alias instead of by IP address.

An example of when this is helpful is having a database in one container and your app in another.

### Mount a bind mount to a container

`docker run --mount type=bind,src=/path/on/local,target=/path/in/container`

### Mount a volume to a container

`docker run --mount type=volume,src=todo-db,target=/path/in/container`

## Best Practices

### Debugging Images

You can check the layers of an image using `docker image history <image>`.

### Layer Caching

When one part of a layer changes all of the layers afterwards have to change/update too. This is why you'll see dependencies as their own layer separate from the source code. If they weren't, then any change to the source would trigger re-installing the dependencies.

### Multi-Stage Builds

Multi-stage builds are useful when your app needs some tools to produce the app from the source code but those tools aren't needed afterwards. An example is the UI of a web app where you'll maybe use Webpack to wrangle all of your code together but you're producing static html/css/js files afterwards.

Building docker containers can be split up into different parts called _stages_. The stages all live within the `Dockerfile` but are separated by newlines. It almost looks like if there are multiple containers/dockerfiles inside one. Here's an example from the docs for a React app:
```
# syntax=docker/dockerfile:1
FROM node:18 AS build
WORKDIR /app
COPY package* yarn.lock ./
RUN yarn install
COPY public ./public
COPY src ./src
RUN yarn run build

FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
```