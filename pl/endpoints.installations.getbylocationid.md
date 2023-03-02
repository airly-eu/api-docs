### GET /v2/installations/{locationId} | endpoints.installations.getbylocationid

Operacja zwraca dane pojedynczej instalacji wskazanej identyfikatorem `locationId`, w odpowiedzi zawsze znajduje się instalacja obecnie funkcjonująca.

Parametry wymagane:
- **locationid** (_integer_) - parametr w ścieżce url; identyfikator lokalizacji

^^^

### Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/location?locationId=8077'
```
