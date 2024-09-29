FROM nextcloud

ARG GID

RUN groupadd -g ${GID} viewer && \
    usermod -g www-data www-data && \
    usermod -a -G viewer www-data
