## Pomiary | endpoints.measurements

Operacje z grupy `/v2/measurements/` umożliwiają pobieranie danych pomiarowych według różnych kryteriów. Wszystkie operacje zwracają jednolity format odpowiedzi, która zawiera następujące pola:
- **current** - pojedynczy element typu _AveragedValues_; zawiera uśrednione pomiary dla ostatnich 60 minut (średnia krocząca); dla stacji pomiarowych innych niż Airly (np. GIOŚ) może zawierać dane do 3 godzin wstecz, z uwagi na opóźnienia w przesyłaniu danych przez GIOŚ
- **history** - lista elementów typu _AveragedValues_; zawiera listę historycznych średnich pomiarów godzinowych, za ostatnie 24 pełne godziny
- **forecast** - lista elementów typu _AveragedValues_; zawiera listę prognozowanych średnich pomiarów godzinowych, dla kolejnych 24 pełnych godzin

::: tip
Pole `history` zawiera dane dla **24 ostatnich pełnych godzin**, tzn. przykładowo jeżeli aktualnie jest godzina 09:27 UTC, to pole będzie zawierać 24 elementy, z których pierwszy zawiera dane dla przedziału czasu 09:00-10:00 UTC poprzedniego dnia, a ostatni dla przedziału 08:00-09:00 UTC dziś.

Natomiast pole `forecast` zawiera prognozowane dane dla **24 kolejnych pełnych godzin**, przy czym pierwsza godzina to aktualna godzina; przykładowo jeżeli aktualnie jest godzina 09:27 UTC, to pole będzie zawierać 24 elementy, z których pierwszy zawiera dane dla przedziału czasu 09:00-10:00 UTC dziś, a ostatni dla przedziału 08:00-09:00 UTC następnego dnia.

Warto zauważyć że pola history oraz forecast tworzą nieprzerwany ciąg danych dla 48 godzin, z których pierwsze 24 godziny stanowią wartości zmierzone, a kolejne 24 godziny to wartości prognozowane.

Pole `current` zawiera średnie dane pomiarowe za **ostatnie 60 minut** (średnia krocząca) licząc od "teraz", tj. od momentu wysłania zapytania. Przykładowo jeśli aktualnie jest godzina 09:27 UTC, to pole to zawiera dane dla przedziału czasu 08:27-09:27 UTC. Przy czym dla instalacji innych niż Airly (np. stacje GIOŚ) pole to może zawierać dane do 3 godzin wstecz, z uwagi na opóźnienia w przesyłaniu danych przez podmioty zewnętrzne.
:::

Obiekt **AveragedValues** składa się z pól:
- **fromDateTime** / **tillDateTime** (_string_) - znacznik czasu w formacie ISO8601; zawiera datę i czas w odniesieniu do strefy UTC; pola w odpowiedzi oznaczają przedział czasu dla którego zostały zebrane i uśrednione dane pomiarowe z danej instalacji, lub na danym obszarze
- **values** - lista obiektów typu value; pojedynczy obiekt składa się z pól
    - **name** (_string_) - nazwa (typ) danego pomiaru; np. PM10
    - **value** (_double_) - zmierzona wielkość pomiarowa; np. stężenie 25µg/m<sup>3</sup>
- **indexes** - lista obiektów typu _Index_; pojedynczy obiekt reprezentuje wartość indeksu obliczonego dla danych pomiarowych zawartych w values
    - **name**  (_string_) - nazwa obliczonego indeksu (np. CAQI, albo PIJP)
    - **value** (_double_) -  wartość numeryczna obliczonego indeksu
    - **level** (_string_) -  [poziom indeksu](#endpoints.meta.indexes) (np. HIGH, albo LOW itp)
    - **description** (_string_) -  tekstowy opis danego poziomu zanieczyszczeń; wartość pola jest zwracana w języku wedle nagłówka `Accept-Language`
    - **advice** (_string_) -  dodatkowy tekst zawierający zalecenia dot. danego poziomu zanieczyszczeń; wartość pola jest zwracana w języku wedle nagłówka `Accept-Language`
    - **color** (_string_) -  kolor odpowiadający danemu poziomowi indeksu; w formacie heksadecymalnym RGB (np. #D1CF1E)
- **standards** - lista obiektów typu _Standard_; pojedynczy obiekt reprezentuje określony standard jakości powietrza
    - **name** (_string_) -  nazwa standardu; aktualnie jedynie standardy WHO
    - **pollutant** (_string_) -  nazwa typu pomiaru dla którego określony jest standard jakości, aktualnie wspierane są PM10 oraz PM25
    - **limit** (_double_) -  poziom stężenia danego zanieczyszczenia, który nie powinien być przekraczany w danym okresie czasu; inaczej, wartość dla której stężenie osiąga 100% normy
    - **percent** (_double_) -  wartość stężenia danego zanieczyszczenia wyrażona jako procentowy udział tego stężenia w normie / limicie; np. dla stężenia PM10 25µg/m<sup>3</sup>, wartość procentowa względem normy 50µg/m<sup>3</sup> wynosi 50%.

<p>&nbsp;</p>

Parametry zapytań wspólne dla wszystkich operacji:
- **indexType** - określa typ indeksu jaki ma być obliczony i zwrócony w odpowiedzi dla danych pomiarowych; wspierane wartości to aktualnie: AIRLY_CAQI (domyślna), CAQI, oraz PIJP; (w obecnej wersji API zwracany jest tylko jeden wybrany indeks)
- **indexPollutant** - określa zbiór rodzajów zanieczyszczeń jakie mają być brane pod uwagę podczas wyliczania wartości obliczanego indeksu, wspierane wartości to aktualnie: PM (domyślna = {PM10, PM25}), PM10, PM25, O3, NO2, SO2, CO, ALL (zbiór wszystkich podanych)


^^^

### Przykład obiektu Measurements

```json
{
  "current": {
    "fromDateTime": "2018-08-24T08:24:48.652Z",
    "tillDateTime": "2018-08-24T09:24:48.652Z",
    "values": [
      { "name": "PM1",          "value": 12.73   },
      { "name": "PM25",         "value": 18.7    },
      { "name": "PM10",         "value": 35.53   },
      { "name": "PRESSURE",     "value": 1012.62 },
      { "name": "HUMIDITY",     "value": 66.44   },
      { "name": "TEMPERATURE",  "value": 24.71   },
      ...
    ],
    "indexes": [
      {
        "name": "AIRLY_CAQI",
        "value": 35.53,
        "level": "LOW",
        "description": "Dobre powietrze.",
        "advice": "Możesz bez obaw wyjść na zewnątrz.",
        "color": "#D1CF1E"
      }
    ],
    "standards": [
      {
        "name": "WHO",
        "pollutant": "PM25",
        "limit": 25,
        "percent": 74.81
      },
      ...
    ]
  },
  "history": [ ... ],
  "forecast": [ ... ]
}
```
