### GET /v2/measurements/point | endpoints.measurements.point

Operacja zwraca pomiary dla dowolnego punktu na mapie.

Wartości pomiarowe interpolowane są z okolicznych sensorów (leżących w odległości do 1,5km od punktu). Wartość pomiaru wyliczana jest jako średnia ważona z okolicznych sensorów, z wagą odwrotnie proporcjonalną do odległości sensora od zadanego punktu.

Parametry wymagane:
- **lat** (_double_) - szerokość geograficzna punktu w postaci dziesiętnej, np. 50.062006
- **lng** (_double_) -  długość geograficzna punktu w postaci dziesiętnej, np. 19.940984

^^^

### Przykład zapytania

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/measurements/point?lat=50.062006&lng=19.940984'
```
