### GET /v2/meta/standards | endpoints.meta.standards

Operacja zwraca listę typów standardów jakości powietrza dostępnych w API wraz z maksymalnymi, dopuszczalnymi wartościami stężeń dla poszczególnych składników zanieczyszczenia powietrza.

Lista zawiera obiekty typu _StandardType_, które zawierają następujące pola:
- **name** (_string_) - nazwa typu standard, np. WHO
- **standardLimits** - mapa klucz-wartość z maksymalnymi wartościami stężeń składników zanieczyszczenia powietrza zdefiniowanych przez standard, zawsze w µg/m³

^^^

### Przykład zapytania:

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/meta/standards'
```

### Przykład odpowiedzi

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
