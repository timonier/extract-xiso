FROM ubuntu:latest

LABEL \
    maintainer="Morgan Auchede <morgan.auchede@gmail.com>"

ENV \
    EXTRACT_XISO_VERSION=latest

RUN set -ex \
\
    # Prepare system
\
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get update \
\
    # Install packages
\
    && export BUILD_DEPS="build-essential ca-certificates curl" \
    && apt-get install --no-install-recommends --yes \
           ${BUILD_DEPS} \
\
    # Install extract-xiso
\
    && export $(curl --location "https://github.com/timonier/version-lister/raw/generated/_/extract-xiso/${EXTRACT_XISO_VERSION}" | xargs) \
    && curl --location "http://downloads.sourceforge.net/project/extract-xiso/extract-xiso%20source/extract-xiso-${EXTRACT_XISO_VERSION}.tar.gz" | tar --directory /tmp --extract --gzip \
    && make --directory /tmp/extract-xiso \
    && mv /tmp/extract-xiso/extract-xiso /usr/bin/extract-xiso \
\
    # Install timonier/dumb-entrypoint
\
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/dumb-entrypoint/installer" | INSTALL_DIRECTORY="/usr/sbin" sh -s -- install \
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/dumb-init/installer" | INSTALL_DIRECTORY="/usr/sbin" sh -s -- install \
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/gosu/installer" | INSTALL_DIRECTORY="/usr/sbin" sh -s -- install \
\
    # Clean
\
    && apt-get remove --purge --yes \
           ${BUILD_DEPS} \
    && apt-get autoremove --purge --yes \
    && rm --force --recursive \
           /tmp/* \
           /var/lib/apt/lists/*

ENTRYPOINT [ "dumb-init" , "--" , "dumb-entrypoint" ]
