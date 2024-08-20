FROM eclipse-temurin:22

RUN apt-get -y update && \
    apt-get -y install --no-install-recommends \
        ca-certificates \
        curl \
        fontconfig \
        git \
        bash \
        openssl \
        sqlite3 \
        tar \
        tzdata && \
    adduser --disabled-password --home /home/container container && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

USER container
ENV USER=container HOME=/home/container
WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD [ "/bin/bash", "/entrypoint.sh" ]
