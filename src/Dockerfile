FROM debian:stable-slim

LABEL \
    maintainer="Morgan Auchede <morgan.auchede@gmail.com>"

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
    # Install dumb-entrypoint
\
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/dumb-entrypoint/installer" | sh -s -- install \
    && curl --location "https://github.com/timonier/dumb-entrypoint/raw/master/src/gosu/installer" | sh -s -- install \
\
    # Install extract-xiso
\
    && export $(curl --location "https://github.com/timonier/version-lister/raw/generated/_/extract-xiso/latest" | xargs) \
    && curl --location "${EXTRACT_XISO_SOURCE}" | tar --directory /tmp --extract --gzip \
    && make --directory /tmp/extract-xiso \
    && mv /tmp/extract-xiso/extract-xiso /usr/local/bin/extract-xiso \
\
    # Clean
\
    && apt-get remove --purge --yes ${BUILD_DEPS} \
    && apt-get autoremove --purge --yes \
    && rm -f -r /tmp/* /var/lib/apt/lists/*

ENTRYPOINT [ "dumb-entrypoint" ]
