ARG BUILD_FROM
FROM $BUILD_FROM

# Installera systemberoenden
RUN apk add --no-cache \
    python3 \
    py3-pip \
    gcc \
    musl-dev \
    libffi-dev \
    openssl-dev \
    bash \
    curl \
    git

# Arbetsmapp
WORKDIR /app

# Virtuell miljö
RUN python3 -m venv /app/venv
ENV PATH="/app/venv/bin:$PATH"

# Uppgradera pip i venv
RUN pip install --upgrade pip

# Installera Litecom2MQTT direkt från GitHub
RUN pip install --no-cache-dir git+https://github.com/swissmanu/litecom2mqtt.git

# Startkommando
CMD ["litecom2mqtt"]
