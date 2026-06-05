# Use Debian Trixie slim image
FROM debian:trixie-slim

# Labels
LABEL author="Amir Y.P" maintainer="myrprhwdnyq@gmail.com"
LABEL org.opencontainers.image.source="https://github.com/amir16yp/yolks"
LABEL org.opencontainers.image.licenses=MIT

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive
ENV USER=container
ENV HOME=/home/container

# Install necessary packages and create container user
RUN apt update && apt upgrade -y \
    && apt install -y \
        gcc g++ libgcc1 libc++-dev gdb libc6 git wget curl tar zip unzip \
        binutils xz-utils liblzo2-2 cabextract iproute2 net-tools \
        netcat-openbsd telnet libatomic1 libsdl1.2debian libsdl2-2.0-0 \
        libfontconfig1 libicu-dev icu-devtools libunwind8 libssl-dev \
        sqlite3 libsqlite3-dev libmariadb-dev libmariadb-dev-compat \
        locales ffmpeg gnupg2 apt-transport-https \
        ca-certificates tzdata liblua5.4-0 liblua5.4-dev libz-dev rapidjson-dev \
    && update-locale LANG=en_US.UTF-8 \
    && dpkg-reconfigure --frontend noninteractive locales \
    && useradd -m -d /home/container -s /bin/bash container
# Switch to container user
USER container

# Set working directory
WORKDIR /home/container

# Copy entrypoint
COPY ./entrypoint.sh /entrypoint.sh

# Set default command
CMD ["/bin/bash", "/entrypoint.sh"]
