FROM ubuntu:14.04
MAINTAINER Stephane Jourdan <sjourdan@greenalto.com>
ENV REFRESHED_AT 2015-11-22
ENV GNATPRO_VERSION=7.4.0
ENV GNAT_SRC_DIR=/src

RUN apt-get update -yqq \
    && apt-get install -yqq make expect

RUN mkdir ${GNAT_SRC_DIR}
COPY ./scripts/expect.sh ${GNAT_SRC_DIR}/

COPY ./src/gnat/gnatpro-${GNATPRO_VERSION}-x86_64-linux-bin.tar.gz ${GNAT_SRC_DIR}

WORKDIR ${GNAT_SRC_DIR}
RUN tar xfz ${GNAT_SRC_DIR}/gnatpro-${GNATPRO_VERSION}-x86_64-linux-bin.tar.gz \
    && cd ${GNAT_SRC_DIR}/gnatpro-${GNATPRO_VERSION}-x86_64-linux-bin \
    && expect ${GNAT_SRC_DIR}/expect.sh \
    && rm -rf ${GNAT_SRC_DIR}

RUN apt-get remove --purge -yqq expect \
    && apt-get autoremove -yqq \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /

ENV PATH /usr/gnat/bin:$PATH
RUN echo "export PATH" >> /etc/profile
