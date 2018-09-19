## Czas | general.time

Wszystkie wartości czasu występujące w API (zarówno jako parametry zapytań, oraz jako pola w odpowiedziach) są w formacie [ISO8601](https://en.wikipedia.org/wiki/ISO_8601) w odniesieniu do strefy [UTC](https://en.wikipedia.org/wiki/Coordinated_Universal_Time) np. `2018-08-24T08:24:48.652Z`.

Średnie wartości pomiarowe wyliczane dla określonego przedziału czasu (np. średnie godzinowe) zwracane są wraz z przedziałem czasu, którego dotyczą. Przedział ten jest podany jako para atrybutów `fromDateTime` oraz `tillDateTime` i jest to przedział lewostronnie domknięty i prawostronnie otwarty `[fromDateTime, tillDatetime)`.

^^^
