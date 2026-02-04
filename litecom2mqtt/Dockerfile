ARG BUILD_FROM
FROM $BUILD_FROM

# Install system dependencies
RUN apk add --no-cache python3 py3-pip

# Set workdir
WORKDIR /app

# Install litecom2mqtt
RUN pip3 install --no-cache-dir litecom2mqtt

# Run application
CMD ["litecom2mqtt"]

