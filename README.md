
# Litecom2MQTT – Home Assistant Add-on (Custom)

Detta add-on kör community-projektet `litecom2mqtt` för att exponera Zumtobel LITECOM via MQTT och Home Assistant discovery.

## Snabbstart
1. **Redigera** `config.json` → `environment`-värden och byt ut `CHANGE_ME_*` till din miljö.
2. Lägg denna mapp i ett eget GitHub-repo *eller* i din lokala custom add-on-repository på Home Assistant (via Samba share `addons/`).
3. I Home Assistant: *Settings → Add-ons → Add-on store → ⋮ (uppe till höger) → Repositories* och lägg till URL:en till ditt repo (eller så dyker add-on:et upp automatiskt om du använder lokalt repo).
4. Installera **Litecom2MQTT**, starta och kolla loggen.

### Obligatoriska variabler (i `environment`)
- `LITECOM2MQTT_MQTT_BROKER_HOST` – IP/host för din MQTT-broker (t.ex. Mosquitto).
- `LITECOM2MQTT_LITECOM_HOST` – IP till din LITECOM CCD.
- `LITECOM2MQTT_LITECOM_CONSUMER_NAME` – fritt namn, t.ex. `HomeAssistant`.
- `LITECOM2MQTT_LITECOM_CONSUMER_API_KEY` – API-nyckeln från LITECOMs **REST API & MQTT**-app.

> Övriga variabler har rimliga standardvärden men kan justeras.

## Tips
- Säkerställ att LITECOMs **REST API & MQTT**-app är installerad och att en **consumer** är skapad.
- Testa publicering/subscribe med MQTT Explorer om felsökning behövs.

## Källor
- litecom2mqtt: https://github.com/swissmanu/litecom2mqtt
- Zumtobel LITECOM – REST API & MQTT manual

