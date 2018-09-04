## Współrzędne geograficzne | general.coordinates

Wszystkie współrzędne geograficzne występujące w API (zarówno jako parametry zapytań, oraz jako pola w odpowiedziach) są współrzędnymi w odniesieniu systemu [WGS 84](https://en.wikipedia.org/wiki/World_Geodetic_System).

Pola `latitude` (lub `lat`) oznaczają szerokość geograficzną, zaś `longitude` (`lng`) długość geograficzną.

Współrzędne podane są jako [stopnie dziesiętne](https://en.wikipedia.org/wiki/Decimal_degrees) w postaci liczby zmiennoprzecinkowej w formacie double, tzn. bez minut i sekund kątowych, za to z częścią dziesiętną reprezentującą ułamkową część stopnia.

Pole `latitude` (`lat`) może przyjmować wartości od -90.0 do +90.0, zaś pole `longitude` (`lng`) wartości od -180.0 do +180.0.

^^^

### Przykłado zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    "https://airapi.airly.eu/v2/installations/204"
```

### Odpowiedź

```json
{
  "id": 204,
  "location": {
    "latitude": 50.062006,
    "longitude": 19.940984
  },
  ...
}
```
