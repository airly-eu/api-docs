### GET /v2/installations/nearest | endpoints.installations.nearest

Operacja zwraca listę instalacji, które znajdują się najbliżej określonego punktu, posortowane według odległości od tego punktu.

Parametry wymagane:
- **lat** (_double_) - szerokość geograficzna punktu w postaci dziesiętnej, np. 50.062006
- **lng** (_double_) -  długość geograficzna punktu w postaci dziesiętnej, np. 19.940984

Parametry opcjonalne:
- **maxDistanceKM** (_double_) -  domyślna wartość 3.0; określa limit odległości w kilometrach w jakiej od określonego punktu muszą leżeć wszystkie znalezione instalacje; wartość ujemna oznacza brak limitu
- **maxResults** (_integer_) -  domyślna wartość 1.0; określa limit instalacji zwróconych w odpowiedzi; wartość ujemna oznacza brak limitu

^^^

### Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/installations/nearest?lat=50.062006&lng=19.940984&maxDistanceKM=5&maxResults=3'
```
