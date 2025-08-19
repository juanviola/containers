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
    nmap \
    jq \
    # Agregamos dependencias para Docker
    ca-certificates \
    gnupg \
    lsb-release \
    && mkdir -p /etc/apt/keyrings \
    # Agregamos la clave GPG oficial de Docker
    && curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg \
    # Agregamos el repositorio de Docker
    && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list > /dev/null \
    # Actualizamos e instalamos Docker CLI
    && apt-get update \
    && apt-get install -y docker-ce-cli \
    # Limpiamos la caché
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /root

CMD ["tail", "-f", "/dev/null"]

