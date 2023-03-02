### GET /v2/installations/{locationId} | endpoints.installations.getbylocationid

Endpoint returns single installation metadata, given by `locationId`, response will always contain currently working installation.

Parametry wymagane:
- **locationId** (_integer_) - url path parameter; location identifier

^^^

### Example request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/location?locationId=8077'
```
