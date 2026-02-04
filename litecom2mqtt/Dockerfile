##############################################
# Litecom2MQTT Home Assistant Add-on Dockerfile
##############################################

# Basimage för HA add-ons
ARG BUILD_FROM=ghcr.io/home-assistant/amd64-base:latest
FROM ${BUILD_FROM}

# Metadata
LABEL io.hass.name="Litecom2MQTT"
LABEL io.hass.description="Bridge Zumtobel Litecom CCD to MQTT with Home Assistant discovery."
LABEL io.hass.arch="amd64"
LABEL io.hass.type="addon"
LABEL io.hass.version="0.1.0"
LABEL maintainer="YourName <you@example.com>"

# Installera beroenden
RUN apk add --no-cache \
    python3 \
    py3-pip \
    bash \
    curl \
    git \
    gcc \
    musl-dev \
    libffi-dev \
    openssl-dev

# Skapa arbetskatalog
WORKDIR /app

# Skapa virtual environment
RUN python3 -m venv /app/venv
RUN /app/venv/bin/pip install --upgrade pip

# Klona Litecom2MQTT-repo
RUN git clone https://github.com/swissmanu/litecom2mqtt.git /app/litecom2mqtt

# Ge rättigheter (om behövs)
RUN chmod -R 755 /app/litecom2mqtt

# Startkommando för add-on
CMD ["/app/venv/bin/python", "/app/litecom2mqtt/litecom2mqtt.py"]
