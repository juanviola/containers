FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    curl \
    dnsutils \
    iputils-ping \
    iproute2 \
    mysql-client \
    netcat-openbsd \
    net-tools \
    tcpdump \
    telnet \
    traceroute \
    wget \
    vim \
    htop \
    jq \
    # clean cache
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /root

CMD ["tail", "-f", "/dev/null"]

