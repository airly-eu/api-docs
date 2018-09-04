### GET /v2/installations/{installationId} | endpoints.installations.getbyid

Endpoint returns single installation metadata, given by `installationId`.

Required parameters;
- **installationId** (_integer_) - url path parameter; installation identifier

^^^

### Example request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    https://airapi.airly.eu/v2/installations/204
```
