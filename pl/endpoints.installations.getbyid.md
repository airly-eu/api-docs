### GET /v2/installations/{installationId} | endpoints.installations.getbyid

Operacja zwraca dane pojedynczej instalacji wskazanej identyfikatorem `installationId`.

Parametry wymagane:
- **installationId** (_integer_) - parametr w ścieżce url; identyfikator instalacji

^^^

### Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    https://airapi.airly.eu/v2/installations/204
```
