### GET /v2/meta/indexes | endpoints.meta.indexes

Operacja zwraca listę typów indeksów dostępnych w API wraz z listą poziomów zdefiniowanych w ramach danego indeksu.

Lista zawiera obiekty typu IndexType, które zawierają następujące pola:
- **name** (_string_) - nazwa typu indeksu, np. AIRLY_CAQI
- **levels** - lista definicji poziomów indeksu, obiekty typu _IndexLevel_ zawierające:
    - **values** (_string_)- tekstowy opis zakresu wartości danego indeksu obejmującego ten poziom, np. 0-25
    - **level** (_string_) - nazwa poziomu indeksu np. "VERY_LOW"
    - **description** (_string_) - opis poziomu indeksu (pole tłumaczone), np. "Bardzo Niski"
    - **color** (_string_) - wartość koloru dla tego poziomu indeksu (np. "#6BC926)

^^^

### Przykład zapytania:

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/meta/indexes'
```

### Przykład odpowiedzi

```json
[
  {
    "name": "AIRLY_CAQI",
    "levels": [
      {
        "values": "0-25",
        "level": "VERY_LOW",
        "description": "Very Low",
        "color": "#6BC926"
      },
      ...
    ]
  },
  ...
]
```
