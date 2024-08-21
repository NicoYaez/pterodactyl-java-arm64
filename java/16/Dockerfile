FROM        eclipse-temurin:16-jammy

LABEL       author="NicoYaez" maintainer="nicoyaez1799@gmail.com"
LABEL       org.opencontainers.image.source="https://github.com/NicoYaez/pterodactyl-java-arm64"
LABEL       org.opencontainers.image.licenses="MIT"

RUN         apt-get update -y \
            && apt-get install -y --no-install-recommends curl ca-certificates openssl git tar sqlite3 fontconfig libfreetype6 libstdc++6 lsof build-essential tzdata iproute2 locales \
            && apt-get clean \
            && rm -rf /var/lib/apt/lists/* \
            && useradd -m -d /home/container container \
            && locale-gen en_US.UTF-8

ENV         LC_ALL=en_US.UTF-8
ENV         LANG=en_US.UTF-8
ENV         LANGUAGE=en_US.UTF-8

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
