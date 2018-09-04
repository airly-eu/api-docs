## Uwierzytelnianie | general.authentication

Korzystanie z API wymaga utworzenia konta użytkownika. Alternatywnie, możliwe jest logowanie istniejącym kontem GitHub, Google lub Facebook.

Po zarejestrowaniu zostaje wygenerowany klucz `apikey`, którym należy uwierzytelniać wszystkie zapytania do API. Klucz można podać albo w dodatkowym nagłówku http o nazwie `apikey` albo jako parametr zapytania.

^^^

## Nagłówek

W celu uwierzytelnienia zapytania do Airly API należy przekazać nagłówek `apikey` z wartością klucza.

```
apikey: {{ apikey }}
```

## Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/meta/indexes'
```

