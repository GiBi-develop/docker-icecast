FROM debian:bookworm-slim

RUN apt update \
    && apt install -y icecast2 \
    && apt install -y media-types \
    && ln -sf /dev/stdout /var/log/icecast2/access.log \
    && ln -sf /dev/stderr /var/log/icecast2/error.log \
    && apt-get -y autoclean \
    && apt-get clean

USER icecast2

CMD ["icecast2", "-c", "/etc/icecast2/icecast.xml"]
