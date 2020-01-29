## Błędy | general.errors

Poprawnie wykonane zapytania do API zwracają kod HTTP `200 OK` oraz odpowiedź w formacie JSON. W pozostałych przypadkach zwracany jest kod błędu HTTP adekwatny do sytuacji. Ilustruje to poniższa tabela:

<table>
    <tr><td>400 - Bad Request            </td><td> zapytanie było niepoprawne, np. użyto niepoprawnych wartości parametrów</td></tr>
    <tr><td>401 - Unauthorized           </td><td> nie podano klucza API (apikey)</td></tr>
    <tr><td>404 - Not Found              </td><td> zapytanie lub ścieżka url wskazują na nieistniejący zasób</td></tr>
    <tr><td>406 - Method Not Allowed     </td><td> zapytanie HTTP korzysta z niedozwolonej metody (np. POST zamiast GET)</td></tr>
    <tr><td>406 - Not Acceptable         </td><td> zapytano o odpowiedź w niewspieranym formacie (np. Accept text/xml zamiast application/json)</td></tr>
    <tr><td>429 - Too Many Requests      </td><td> przekroczono limit zapytań API (patrz <a href="#general.limits">Limity</a>)</td></tr>
    <tr><td>500 - Internal Server Error  </td><td> wystąpił błąd serwera Airly</td></tr>
</table>

Ponadto w przypadku błędu zwrócona zostaje odpowiedź w formacie JSON o następującej treści:

```json
{
  "errorCode": "kod błędu",
  "message": "opis błędu",
  "details": {
    <mapa klucz-wartość z dodatkowymi szczegółami błędu>
  }
}
```

^^^

### Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/point?lat=200&lng=19.940984'
```

### Odpowiedź

```
HTTP Status: 400
```
```json
{
  "errorCode": "API_REQUEST_INVALID",
  "message": "API Request was not valid",
  "details": {
    "violations": [
      {
        "parameter": "lat",
        "message": "latitude value must be between -90.0 and +90.0",
        "rejectedValue": 200
      }
    ]
  }
}
```
