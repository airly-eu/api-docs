### GET /v2/measurements/installation | endpoints.measurements.installation

Endpoint returns measurements for concrete installation given by `installationId`.

In case of the installation does not exist, or it was already deinstalled, returns `404 Not Found`.

In case of the installation was replaced with another device, returns `301 Moved Permanently` with `Location` header pointing to new URL of this installation's replacement measurements.

Required parameters:
- **installationId** (_integer_) - installation identifier

^^^

### Example request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/installation?installationId=204'
```
