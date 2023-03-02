### GET /v2/measurements/location | endpoints.measurements.location

Endpoint returns measurements for concrete location given by `locationId`.

In case of the location does not exist, or it does not have any installation, returns `404 Not Found`.

Parametry wymagane:
- **locationid** (_integer_) - location identifier

^^^

### Example request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/location?locationId=8077'
```
