
# Litecom2MQTT – Home Assistant Add-on

Kör community-projektet `litecom2mqtt` som brygga mellan Zumtobel LITECOM och MQTT (Home Assistant Discovery).

## Snabbstart
1. Installera add-on:et från denna repository i Add-on Store.
2. Öppna **Configuration** och uppdatera `environment`‑variablerna (`CHANGE_ME_*`).
3. Starta add-on:et och kontrollera loggen.

## Miljövariabler (viktiga)
- `LITECOM2MQTT_MQTT_BROKER_HOST` – din MQTT broker (Mosquitto).
- `LITECOM2MQTT_LITECOM_HOST` – IP till LITECOM CCD.
- `LITECOM2MQTT_LITECOM_CONSUMER_API_KEY` – API‑nyckel från LITECOM (REST API & MQTT → Consumers).
- 

