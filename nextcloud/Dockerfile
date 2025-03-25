FROM nextcloud:30.0.4

ARG GID

RUN groupadd -g ${GID} viewer && \
    usermod -g www-data www-data && \
    usermod -a -G viewer www-data
