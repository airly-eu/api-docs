### GET /v2/measurements/installation | endpoints.measurements.installation

Operacja zwraca pomiary dla konkretnej instalacji danej parametrem `installationId`.

W przypadku gdy dana instalacja nie istnieje, lub gdy sensor w danym miejscu został zdemontowany, zwraca status `404 Not Found`.

W przypadku gdy instalacja w danym miejscu została zastąpiona innym urządzeniem, zwraca status `301 Moved Permanently` wraz z nagłówkiem `Location` prowadzącym do URL z pomiarami nowej instalacji.

Parametry wymagane:
- **installationId** (_integer_) - identyfikator instalacji

^^^

### Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/installation?installationId=204'
```
