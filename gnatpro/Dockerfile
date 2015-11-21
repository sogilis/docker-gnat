FROM ubuntu:14.04
ENV GNATPRO_VERSION=7.4.0
ENV GNAT_SRC_DIR=/src

RUN apt-get update \
    && apt-get install -y make expect

RUN mkdir ${GNAT_SRC_DIR}

COPY ./src/gnat/gnatpro-${GNATPRO_VERSION}-x86_64-linux-bin.tar.gz ${GNAT_SRC_DIR}

WORKDIR ${GNAT_SRC_DIR}

RUN tar xfz /src/gnatpro-${GNATPRO_VERSION}-x86_64-linux-bin.tar.gz

WORKDIR ${GNAT_SRC_DIR}/gnatpro-${GNATPRO_VERSION}-x86_64-linux-bin
COPY ./scripts/expect.sh .
RUN expect expect.sh

RUN echo "export PATH=/usr/gnat/bin:$PATH" >> ~/.bashrc

RUN rm -rf ${GNAT_SRC_DIR}
RUN apt-get remove --purge -y expect \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /
