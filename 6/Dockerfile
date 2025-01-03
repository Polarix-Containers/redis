ARG VERSION=6
ARG UID=3008
ARG GID=3008

FROM redis:${VERSION}-alpine

ARG UID
ARG GID

LABEL maintainer="Thien Tran contact@tommytran.io"

RUN apk -U upgrade \
    && apk add libstdc++ shadow \
    && rm /usr/local/bin/gosu

RUN --network=none \
    usermod -u ${UID} redis \
    && groupmod -g ${GID} redis \
    && find / -user 999 -exec chown -h redis {} \; \
    && find / -group 1000 -exec chgrp -h redis {} \; \
    && apk del shadow \
    && rm -rf /var/cache/apk/*


COPY --from=ghcr.io/polarix-containers/hardened_malloc:latest /install /usr/local/lib/
ENV LD_PRELOAD="/usr/local/lib/libhardened_malloc.so"

USER redis