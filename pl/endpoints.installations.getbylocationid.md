### GET /v2/installations/location | endpoints.installations.getbylocationid

Operacja zwraca dane pojedynczej instalacji wskazanej identyfikatorem `locationId`, w odpowiedzi zawsze znajduje się instalacja obecnie funkcjonująca.

Parametry wymagane:
- **locationId** (_integer_) - parametr w ścieżce url; identyfikator lokalizacji

^^^

### Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/installations/location?locationId=8077'
```
