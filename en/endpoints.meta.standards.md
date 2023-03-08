### GET /v2/meta/standards | endpoints.meta.standards

Endpoint returns a list of all the air quality standard types supported in the API along with maximum, acceptable concentrations per each pollutant.

The returned array contains objects of type _StandardType_, which contain following fields:
- **name** (_string_) - name of this standard type, e.g. WHO
- **standardLimits** - key-value map representing pollutant concentration limits defined by the standard, always in µg/m³

^^^

### Example request:

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/meta/standards'
```

### Example response

```json
[
  {
    "name": "WHO",
    "standardLimits": {
      "CO": 4000.0,
      "NO2": 25.0,
      "PM10": 45.0,
      "PM25": 15.0,
      "O3": 100.0,
      "SO2": 40.0
    }
  },
  ...
]
```
