## Instalacje | concepts.installations

W poprzedniej wersji API operowaliśmy pojęciem sensora. Można było np. zapytać jakie sensory znajdują się na danym obszarze, oraz odpytać poszczególne sensory o ich pomiary za pomocą identyfikatora sensora (sensorId). Niestety takie podejście rodzi pewne problemy. Nasza flota urządzeń cały czas się rozrasta i nie sposób uniknąć sytuacji gdy jakieś urządzenie trzeba np. wymienić na nowe, albo przenieść w inne miejsce. Niestety taka sytuacja może skutkować odpytywaniem o niewłaściwy sensor, np. taki którego już nie ma, albo który został gdzieś przeniesiony.

W nowym API rozwiązujemy ten problem wprowadzając pojęcie instalacji. Instalacja wiąże ze sobą sensor oraz lokalizację, w której jest zamontowany w danym momencie. Można zatem bezpiecznie odpytywać o pomiary konkretną instalację, bez ryzyka, że będzie się pytało o niewłaściwy sensor.

Jeżeli w danym miejscu sensor został zdeinstalowany, to dalsze zapytania o tę samą instalację mogą zwrócić jeden z dwóch rodzajów odpowiedzi:
- jeżeli w tym miejscu nastąpiła wymiana sensora na nowy, to zapytania będą zwracały kod HTTP `301 Moved Permanently` wraz z nagłówkiem `Location` wskazującym na nowy url, który należy odpytać zamiast dotychczasowego. Dodatkowo zwracana jest odpowiedź w formacie JSON

```json
{
    "errorCode": "INSTALLATION_REPLACED",
    "message": "Installation was replaced with another one",
    "details": {
        "successorId": <identyfikator nowej instalacji>
    }
}
```

- jeżeli w tym miejscu nie ma nowego sensora ("następcy") to zapytania będą zwracały kod błędu `404 Not Found`

Zasadniczo zalecamy korzystanie z innych operacji API, np. takich, które zwracają pomiary dla danej lokalizacji lub takich, które zwracają uśrednione pomiary dla danego obszaru. Wówczas nie trzeba przejmować się instalacjami, ich identyfikatorami, itd. Jeśli jednak ktoś chce odpytywać konkretną instalację, musi brać pod uwagę powyższe i stosownie obsługiwać zwracane kody odpowiedzi.

^^^
