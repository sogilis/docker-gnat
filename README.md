# Docker GNAT

This is a collection of GNAT Docker containers.

Goal: access a variety of GNAT versions (like Pro or community) through Docker containers.

## Build

You should have downloaded a `AdaCore-Download-*.tar` file from AdaCore. Untar under `gnatpro/src` so you have something like `./gnatpro/src/gnat/gnatpro-7.4.0-x86_64-linux-bin.tar.gz`

Build the container:
    cd gnatpro
    docker build -t gnatpro:7.4.0 .

You'll now have a fully working GNAT Pro 7.4.0 container image under `docker images gnatpro`

```
docker images gnatpro
REPOSITORY          TAG                 IMAGE ID            CREATED              VIRTUAL SIZE
gnatpro             7.4.0               52daa08ad9fb        About a minute ago   680.9 MB
```

## Run

Simply run the container: 

    docker run -it gnatpro:7.4.0 gnatmake --version
    GNATMAKE Pro 7.4.0 (20151104-49)
    Copyright (C) 1995-2015, Free Software Foundation, Inc.
