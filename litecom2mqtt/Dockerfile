########################################################
# Litecom2MQTT Home Assistant Add-on Dockerfile
# Fullständig, ready-to-run
########################################################

# Bygg från Home Assistant base image
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

# Skapa arbetsmapp
WORKDIR /app

# Skapa och aktivera virtuell miljö
RUN python3 -m venv /app/venv
ENV PATH="/app/venv/bin:$PATH"

# Uppgradera pip inuti venv
RUN pip install --upgrade pip

# Installera Litecom2MQTT i venv
RUN pip install --no-cache-dir litecom2mqtt

# Ange standard-kommando när add-on startar
CMD ["litecom2mqtt"]
