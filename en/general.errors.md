## Errors | general.errors

Correctly issued API requests result in `200 OK` HTTP status and a JSON content. Otherwise an HTTP error code status is returned, depending on situation. Table below explains it in detail:

<table>
    <tr><td>400 - Bad Request            </td><td>request was incorrect, e.g. query parameters were invalid</td></tr>
    <tr><td>401 - Unauthorized           </td><td>no API key was provided</td></tr>
    <tr><td>404 - Not Found              </td><td>request path or parameters point to a non-existent resource</td></tr>
    <tr><td>405 - Method Not Allowed     </td><td>request attempts to use invalid HTTP method (e.g. POST instead of GET)</td></tr>
    <tr><td>406 - Not Acceptable         </td><td>request attempts to use unsupported content type (e.g. Accept text/xml instead of application/json)</td></tr>
    <tr><td>429 - Too Many Requests      </td><td>API rate limit was exceeded (see <a href="#general.limits">Limits</a>)</td></tr>
    <tr><td>500 - Internal Server Error  </td><td>a server error has occured</td></tr>
</table>

Additionally in case of an error a JSON response is returned in following format:

```json
{
  "errorCode": <error code>,
  "message": <message describing error>,
  "details": {
    <key-value map with more details describing the error>
  }
}
```

^^^

### Example request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/point?lat=200&lng=19.940984'
```

### Error response

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
