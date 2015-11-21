# Docker GNAT

This is a collection of GNAT Docker containers.

Goal: access a variety of GNAT versions (like Pro or community) through Docker containers.

## Build

You should have downloaded a `AdaCore-Download-*.tar` file from AdaCore. Untar under `gnatpro/src` so you have something like `./gnatpro/src/gnat/gnatpro-7.4.0-x86_64-linux-bin.tar.gz`

Build the container:

    docker build -t gnatpro:7.4.0 gnatpro

You'll now have a fully working GNAT Pro 7.4.0 container image under `docker images gnatpro`

```
docker images gnatpro
REPOSITORY          TAG                 IMAGE ID            CREATED             VIRTUAL SIZE
gnatpro             7.4.0               25dcf079fca9        16 minutes ago      284.6 MB
gnatpro             4.8                 026cddfbf64a        28 minutes ago      310.7 MB
```

## Run

    docker run -it gnatpro:7.4.0 /usr/gnat/bin/gnatmake --version
    GNATMAKE Pro 7.4.0 (20151104-49)
    Copyright (C) 1995-2015, Free Software Foundation, Inc.
