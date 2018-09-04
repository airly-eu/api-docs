## Authentication | general.authentication

Using our API requires registering an account. It is also possible to log in with existing GitHub, Google or Facebook account.

A registered user is provided with an `apikey` which should be passed on each API request for authentication. The API key can be passed in a request as a custom header named apikey or as a query parameter.

^^^

## Headers

To authenticate, Airly API expects you to pass an `apikey` header with your API key passed in as a value.

```
apikey: {{ apikey }}
```

## Example Request

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    https://airapi.airly.eu/v2/meta/indexes
```

