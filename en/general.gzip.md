## GZIP compression | general.gzip

All the API endpoints support GZIP compression. Enabling compression significantly reduces API response size and can speed up its transfer, and it is a recommended practice.

In order to enable compression an API request should contain additional HTTP header `Accept-Encoding: gzip`. Keep in mind that the HTTP client used for communication should be properly configured to handle compressed responses.

^^^

### Example request

```bash
 curl -X GET -sD - \
    --compressed \
    --header 'Accept: application/json' \
    --header 'Accept-Encoding: gzip' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/installation?installationId=204'
```

### Response

```bash
HTTP/2 200
date: Tue, 18 Sep 2018 13:18:19 GMT
content-type: application/json;charset=UTF-8
...
content-encoding: gzip

{ ... }
```
