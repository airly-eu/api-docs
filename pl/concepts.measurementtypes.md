### Typy pomiarów | concepts.measurementtypes

Nasze urządzenia mierzą szereg różnych wartości: temperaturę, wilgotność, ciśnienie atmosferyczne, stężenia pyłów itd. Nasze API daje jednak dostęp również do danych pochodzących z innych stacji pomiarowych (np. stacji [GIOŚ](http://powietrze.gios.gov.pl/)), które mierzą tylko niektóre z tych parametrów (np. tylko PM10, obecnie nie przetwarzamy i nie udostępniamy innych zanieczyszczeń niż pyłowe). Aby dać dostęp do wszystkich tych danych w sposób jednolity, dane pomiarowe zwracane są w dynamicznej strukturze w postaci listy (json array), której poszczególne elementy to obiekty zawierające parę "nazwa-wartość" dla określonego typu pomiaru.

Listę wszystkich typów pomiarów, które wspiera platforma, ich nazwy oraz stosowane jednostki można pobrać odpytując adres `/v2/meta/measurements`.

^^^
