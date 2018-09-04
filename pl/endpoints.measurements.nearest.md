### GET /v2/measurements/nearest | endpoints.measurements.nearest

Operacja zwraca pomiary dla instalacji najbliższej określonej lokalizacji.

W przypadku gdy w odległości `maxDistanceKM` od punktu nie znaleziono żadnej instalacji, zwraca status `404 Not Found`.

Parametry wymagane:
- **lat** (_double_) - szerokość geograficzna punktu w postaci dziesiętnej, np. 50.062006
- **lng** (_double_) -  długość geograficzna punktu w postaci dziesiętnej, np. 19.940984

Parametry opcjonalne:
- **maxDistanceKM** (_double_) -  domyślna wartość 3.0; określa limit odległości w kilometrach w jakiej od określonego punktu musi leżeć poszukiwana instalacja; wartość ujemna oznacza brak limitu

^^^

### Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/nearest?lat=50.062006&lng=19.940984&maxDistanceKM=5'
```
