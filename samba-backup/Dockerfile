ARG BUILD_FROM=ghcr.io/hassio-addons/base:12.0.0
FROM $BUILD_FROM

ENV LANG C.UTF-8

# Copy script
COPY rootfs /

# Setup base
ARG BUILD_ARCH
ARG CLI_VERSION=4.35.0
RUN \
    curl -Lso /usr/bin/ha "https://github.com/home-assistant/cli/releases/download/${CLI_VERSION}/ha_${BUILD_ARCH}" \
    && chmod a+x /usr/bin/ha \
    && apk add --no-cache \
        samba-client \
    && chmod a+x /run.sh

# Run script
CMD [ "/run.sh" ]