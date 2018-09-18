## Kompresja GZIP | general.gzip

Wszystkie operacje API wspierają kompresję GZIP. Włączenie kompresji znacząco zmniejsza rozmiar danych przesyłanych z API i może skrócić czas ich pobierania i jest to zalecana praktyka. 

W celu włączenia kompresji należy w zapytaniu HTTP przesłać dodatkowy nagłówek `Accept-Encoding: gzip`. Należy zwrócić uwagę aby klient HTTP używany do komunikacji z API był odpowiednio skonfigurowany i obsługiwał skompresowane odpowiedzi.

^^^

### Przykład zapytania

```bash
 curl -X GET -sD - \
    --compressed \
    --header 'Accept: application/json' \
    --header 'Accept-Encoding: gzip' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/installation?installationId=204'
```

### Odpowiedź

```bash
HTTP/2 200
date: Tue, 18 Sep 2018 13:18:19 GMT
content-type: application/json;charset=UTF-8
...
content-encoding: gzip

{ ... }
```
