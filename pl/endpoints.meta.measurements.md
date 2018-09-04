### GET /v2/meta/measurements | endpoints.meta.measurements

Operacja zwraca listę wszystkich typów pomiarów dostępnych w API wraz z ich nazwami i stosowanymi jednostkami.

Lista zawiera obiekty typu MeasurementType, które zawierają następujące pola
- **name** (_string_) - nazwa typu pomiaru, np. PM10
- **label** (_string_) - nazwa opisowa typu pomiaru (pole tłumaczone)
- **unit** (_string_) - jednostka stosowana dla tego typu pomiaru

^^^

### Przykład zapytania:

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/meta/measurements'
```

### Przykład odpowiedzi

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
