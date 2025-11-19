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
    # Instalamos Node.js desde NodeSource
    && curl -fsSL https://deb.nodesource.com/setup_lts.x | bash - \
    && apt-get install -y nodejs \
    # Agregamos la clave GPG de MongoDB
    && curl -fsSL https://pgp.mongodb.com/server-7.0.asc | gpg --dearmor -o /etc/apt/keyrings/mongodb-server-7.0.gpg \
    # Agregamos el repositorio de MongoDB
    && echo "deb [ arch=amd64,arm64 signed-by=/etc/apt/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-7.0.list \
    # Actualizamos e instalamos mongosh
    && apt-get update \
    && apt-get install -y mongodb-mongosh \
    # Instalamos PostgreSQL client
    && apt-get install -y postgresql-client \
    # Limpiamos la caché
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /root

CMD ["tail", "-f", "/dev/null"]

