FROM ubuntu:14.04
RUN apt-get update \
    && apt-get install -y gnat-4.8 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
RUN mkdir /src
WORKDIR /src
ENTRYPOINT ["gnatmake"]
