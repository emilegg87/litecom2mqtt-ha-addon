ARG BUILD_FROM
FROM $BUILD_FROM

# Install dependencies
RUN apk add --no-cache python3 py3-pip gcc musl-dev libffi-dev openssl-dev

# Skapa venv och aktivera
WORKDIR /app
RUN python3 -m venv /app/venv
ENV PATH="/app/venv/bin:$PATH"

# Upgrade pip i venv
RUN pip install --upgrade pip

# Install litecom2mqtt i venv
RUN pip install --no-cache-dir litecom2mqtt

# Kör programmet
CMD ["litecom2mqtt"]
