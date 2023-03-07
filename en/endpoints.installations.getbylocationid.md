### GET /v2/installations/location | endpoints.installations.getbylocationid

Endpoint returns single installation metadata, given by `locationId`, response will always contain currently working installation.

Required parameters:
- **locationId** (_integer_) - url path parameter; location identifier

^^^

### Example request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/installations/location?locationId=8077'
```
