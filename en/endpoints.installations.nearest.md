### GET /v2/installations/nearest | endpoints.installations.nearest

Endpoint returns list of installations which are closest to a given point, sorted by distance to that point.

Required parameters:
- **lat** (_double_) - latitude as decimal degree, e.g. 50.062006
- **lng** (_double_) - longitude as decimal degree, e.g. 19.940984

Optional parameters:
- **maxDistanceKM** (_double_) -  default value 3.0; all the returned installations must be located within this limit from the given point (in km); negative value means no limit
- **maxResults** (_integer_) -  default value 1.0; maximum number of installations to return; negative value means no limit

^^^

### Example request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/installations/nearest?lat=50.062006&lng=19.940984&maxDistanceKM=5&maxResults=3'
```
