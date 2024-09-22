FROM debian:bookworm-slim

EXPOSE 8000

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update \
    && apt install -y --no-install-recommends icecast2 media-types \
    && ln -sf /dev/stdout /var/log/icecast2/access.log \
    && ln -sf /dev/stderr /var/log/icecast2/error.log \
    && apt-get -y autoclean \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

USER icecast2

CMD ["icecast2", "-c", "/etc/icecast2/icecast.xml"]
