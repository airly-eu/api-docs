## Zasady użytkowania oraz limity | general.limits

### Zasady użytkowania

W wersji darmowej dostępu do API użytkownik zobowiązuje się do wykorzystywania API wyłącznie w celach niekomercyjnych.

Obok danych pochodzących z naszego API prezentowanych w aplikacjach należy umieścić nasze logo: [svg](https://cdn.airly.org/assets/brand/logo/primary/airly.svg), [png](https://cdn.airly.org/assets/brand/logo/primary/airly-1024.png).

Więcej szczegółów dotyczących zasad wykorzystania API można znaleźć w naszym [Regulaminie](https://airly.org/pl/regulaminy-polityka-prywatnosci/).

### Limity

W celu zachowania wysokiej przepustowości i jakości usługi dla wszystkich użytkowników, stosujemy limitowanie w dostępie do API.

Domyślny limit dla wszystkich użytkowników wynosi **100** zapytań dziennie dla pojedynczego klucza.

Zliczaniu podlegają wszystkie zapytania HTTP wysyłane do API, niezależnie od tego czy były wykonane poprawnie czy też zwróciły błąd. Każde pojedyncze zapytanie zmniejsza aktualnie dostępny limit o 1. Liczniki resetują się o północy UTC (limit dzienny) oraz o każdej pełnej minucie (limit minutowy).

::: tip
Powyższy limit pozwala np. na odpytywanie o pomiary pojedynczego sensora z częstotliwością co 15 minut przez całą dobę, lub na zbieranie danych z 4 sensorów z częstotliwością co godzinę przez całą dobę, powinien zatem być wystarczający w większości indywidualnych zastosowań.

W przypadku aplikacji które wyświetlają dane w sposób ciągły zalecamy aby zapisywać odpowiedzi API w pamięci lokalnej (cache) i odświeżać je w tle w określonych odstępach czasu.
:::

W przypadku przekroczenia limitu zapytanie do API zwróci status `HTTP 429 - Too Many Requests`.

Jeżeli potrzebujesz zwiększenia swojego limitu API lub chcesz wykorzystać nasze dane w projekcie komercyjnym, [skontaktuj się z nami](https://airly.org/pl/kontakt/).

### Nagłówki RateLimit

Każda odpowiedź z API zawiera dodatkowe nagłówki informujące o limitach obowiązujących używany klucz API oraz o ich aktualnym użyciu. Nazwy nagłówków zaczynają się od `X-RateLimit-Limit-` oraz `X-RateLimit-Remaining-`, np.:
```
X-RateLimit-Limit-day: 100
X-RateLimit-Remaining-day: 96
```

^^^
