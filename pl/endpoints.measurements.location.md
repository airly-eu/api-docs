### GET /v2/measurements/location | endpoints.measurements.location

Operacja zwraca połączone pomiary dla instalacji danych parametrem `locationId`.

W przypadku gdy dana lokalizacja nie istnieje, lub gdy żaden sensor nie działał w ciągu ostatnihc 24 godziny, zwraca status `404 Not Found`.

Parametry wymagane:
- **locationId** (_integer_) - identyfikator lokalizacji

^^^

### Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/location?locationId=8077'
```
