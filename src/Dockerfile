FROM debian:stable-slim

LABEL \
    maintainer="Morgan AUCHEDE <morgan.auchede@gmail.com>"

ENV \
    LC_ALL=C.UTF-8

RUN set -e -u -x \
\
    # Prepare system
\
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
\
    # Install packages
\
    && BUILD_DEPS="build-essential curl" \
    && apt-get install --no-install-recommends --yes ${BUILD_DEPS} ca-certificates locales \
\
    # Install extract-xiso
\
    && curl --location "https://sourceforge.net/projects/extract-xiso/files/extract-xiso%20source/extract-xiso-2.7.1.tar.gz/download" | tar --directory /tmp --extract --gzip \
    && make --directory /tmp/extract-xiso \
    && mv /tmp/extract-xiso/extract-xiso /usr/local/bin/extract-xiso \
\
    # Clean
\
    && apt-get remove --purge --yes ${BUILD_DEPS} \
    && apt-get autoremove --purge --yes \
    && rm -f -r /tmp/* /var/lib/apt/lists/*
