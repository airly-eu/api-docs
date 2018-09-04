### GET /v2/meta/measurements | endpoints.meta.measurements

Endpoint returns list of all the measurement types supported in the API along with their names and units.

The returned array contains objects of type _MeasurementType_ which contain following fields:
- **name** (_string_) - name of this measurement type, e.g. PM10
- **label** (_string_) - descriptive name of this measurement type (field translated)
- **unit** (_string_) - unit of this measurement type e.g. µg/m<sup>3</sup>

^^^

### Example request:

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/meta/measurements'
```

### Example response

```json
[
  {
    "name": "PM10",
    "label": "PM10",
    "unit": "µg/m³"
  },
  {
    "name": "TEMPERATURE",
    "label": "Temperature",
    "unit": "°C"
  },
  ...
]
```
