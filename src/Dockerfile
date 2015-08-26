FROM debian:jessie
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

COPY extract-xiso-2.7.1.tar.gz /tmp/extract-xiso-2.7.1.tar.gz

RUN set -x \
    && BUILD_DEPS='build-essential' \
    && apt-get update \
    && apt-get install -y --no-install-recommends $BUILD_DEPS \
    && tar xvzf /tmp/extract-xiso-2.7.1.tar.gz -C /tmp \
    && cd /tmp/extract-xiso \
    && make \
    && mv extract-xiso /usr/local/bin/extract-xiso \
    && apt-get purge -y --auto-remove $BUILD_DEPS \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENTRYPOINT [ "/usr/local/bin/extract-xiso" ]
