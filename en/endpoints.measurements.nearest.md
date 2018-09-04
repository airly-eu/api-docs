### GET /v2/measurements/nearest | endpoints.measurements.nearest

Endpoint returns measurements for an installation closest to a given location.

If no installation could be found within `maxDistanceKM` from the given point, then returns `404 Not Found`.

Required parameters:
- **lat** (_double_) - latitude as decimal degree, e.g. 50.062006
- **lng** (_double_) - longitude as decimal degree, e.g. 19.940984

Optional parameters:
- **maxDistanceKM** (_double_) -  default value 3.0; the searched installation must be located within this limit from the given point (in km); negative value means no limit

^^^

### Example request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/nearest?lat=50.062006&lng=19.940984&maxDistanceKM=5'
```
