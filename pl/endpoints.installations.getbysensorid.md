### GET /v2/installations/sensor | endpoints.installations.getbysensorid

Operacja zwraca dane pojedynczej instalacji wskazanej identyfikatorem `sensorId`, w odpowiedzi zawsze znajduje się instalacja obecnie funkcjonująca.

Parametry wymagane:
- **sensorId** (_integer_) - parametr w ścieżce url; identyfikator sensora

^^^

### Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/installations/sensor?sensorId=204'
```
