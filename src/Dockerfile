FROM debian:jessie
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    DEBIAN_FRONTEND=noninteractive \
    EXTRACT_XISO_VERSION=2.7.1

RUN set -x \

    # Prepare system

    && apt-get update \

    # Install packages

    && BUILD_DEPS="build-essential curl" \
    && apt-get install -y --no-install-recommends \
           $BUILD_DEPS \

    # Compile extract-xiso

    && curl -sLo /tmp/extract-xiso.tar.gz "http://downloads.sourceforge.net/project/extract-xiso/extract-xiso%20source/extract-xiso-$EXTRACT_XISO_VERSION.tar.gz" \
    && sh -c "cd /tmp && tar xvzf extract-xiso.tar.gz" \
    && make -C /tmp/extract-xiso \
    && mv /tmp/extract-xiso/extract-xiso /usr/bin/extract-xiso \

    # Clean

    && apt-get remove -y --purge \
           $BUILD_DEPS \
    && apt-get autoremove -y --purge \
    && rm -rf \
           /var/lib/apt/lists/* \
           /tmp/*

ENTRYPOINT [ "/usr/bin/extract-xiso" ]
