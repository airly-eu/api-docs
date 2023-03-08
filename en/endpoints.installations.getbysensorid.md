### GET /v2/installations/sensor | endpoints.installations.getbysensorid

Endpoint returns single installation metadata, given by `sensorId`, response will always contain currently working installation.

Required parameters:
- **sensorId** (_integer_) - url path parameter; sensor identifier

^^^

### Example request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/installations/sensor?sensorId=204'
```
