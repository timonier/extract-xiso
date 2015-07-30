FROM debian:jessie
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

COPY extract-xiso-2.7.1.tar.gz /tmp/extract-xiso-2.7.1.tar.gz

RUN apt-get update \
    && apt-get install -y --no-install-recommends build-essential \
    && tar xvzf /tmp/extract-xiso-2.7.1.tar.gz -C /tmp \
    && cd /tmp/extract-xiso \
    && make \
    && mv extract-xiso /usr/local/bin/extract-xiso \
    && apt-get autoremove -y --purge build-essential \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ENTRYPOINT [ "/usr/local/bin/extract-xiso" ]
