### GET /v2/measurements/point | endpoints.measurements.point

Endpoint returns measurements for any geographical location.

Measurement values are interpolated by averaging measurements from nearby sensors (up to 1,5km away from the given point). The returned value is a weighted average, with the weight inversely proportional to the distance from the sensor to the given point.

Required parameters:
- **lat** (_double_) - latitude as decimal degree, e.g. 50.062006
- **lng** (_double_) - longitude as decimal degree, e.g. 19.940984

^^^

### Example request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/point?lat=50.062006&lng=19.940984'
```
