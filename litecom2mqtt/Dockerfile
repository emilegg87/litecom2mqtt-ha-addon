# ===== Basbild =====
ARG BUILD_FROM=ghcr.io/home-assistant/amd64-base:latest
FROM ${BUILD_FROM}

# ===== Metadata =====
LABEL io.hass.type="addon"
LABEL io.hass.name="Litecom2MQTT"
LABEL io.hass.description="Bridge Zumtobel Litecom CCD to MQTT with Home Assistant discovery."
LABEL io.hass.version="0.1.0"
LABEL io.hass.arch="amd64"
LABEL io.hass.url="https://github.com/swissmanu/litecom2mqtt"

# ===== Installera beroenden =====
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

# ===== Skapa arbetskatalog =====
WORKDIR /app

# ===== Hämta Litecom2MQTT direkt från GitHub =====
RUN git clone https://github.com/swissmanu/litecom2mqtt.git /app/litecom2mqtt

# ===== Skapa virtuellt Python-miljö =====
RUN python3 -m venv /app/venv
ENV PATH="/app/venv/bin:$PATH"

# ===== Installera beroenden för Litecom2MQTT =====
RUN pip install --no-cache-dir --upgrade pip setuptools
RUN pip install --no-cache-dir -r /app/litecom2mqtt/requirements.txt

# ===== Exponera ev. portar (valfritt) =====
EXPOSE 3000

# ===== Startkommando =====
CMD [
    "python3",
    "/app/litecom2mqtt/litecom2mqtt.py",
    "--mqtt-host", "${MQTT_HOST}",
    "--mqtt-port", "${MQTT_PORT}",
    "--mqtt-username", "${MQTT_USERNAME}",
    "--mqtt-password", "${MQTT_PASSWORD}",
    "--mqtt-tls", "${MQTT_TLS}",
    "--mqtt-validate-cert", "${MQTT_VALIDATE_CERT}",
    "--litecom-ip", "${LITECOM_IP}",
    "--litecom-port", "${LITECOM_PORT}"
]
