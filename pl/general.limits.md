## Zasady użytkowania oraz limity | general.limits

### Zasady użytkowania

W wersji darmowej dostępu do API użytkownik zobowiązuje się do wykorzystywania API wyłącznie w celach niekomercyjnych.

Obok danych pochodzących z naszego API prezentowanych w aplikacjach należy umieścić nasze [logo](https://airly.eu/wp-content/themes/draftweb/images/presskit/big/logo1.jpg).

Więcej szczegółów dotyczących zasad wykorzystania API można znaleźć w naszym [Regulaminie](https://airly.eu/docs/tos-pl.pdf).

### Limity

W celu zachowania wysokiej przepustowości i jakości usługi dla wszystkich użytkowników, stosujemy limitowanie w dostępie do API.

Domyślne limity dla wszystkich użytkowników wynoszą **1000** zapytań dziennie oraz **50** zapytań na minutę dla pojedynczego klucza.

Zliczaniu podlegają wszystkie zapytania HTTP wysyłane do API, niezależnie od tego czy były wykonane poprawnie czy też zwróciły błąd. Każde pojedyncze zapytanie zmniejsza aktualnie dostępny limit o 1. Liczniki resetują się o północy (limit dzienny) oraz o każdej pełnej minucie (limit minutowy).

::: tip
Powyższe limity pozwalają np. na odpytywanie o pomiary pojedynczego sensora z częstotliwością co 1.5 minuty przez całą dobę, lub na zbieranie danych z 40 sensorów z częstotliwością co godzinę przez całą dobę, powinny zatem być wystarczające w większości indywidualnych zastosowań.

W przypadku aplikacji które wyświetlają dane w sposób ciągły zalecamy aby zapisywać odpowiedzi API w pamięci lokalnej (cache) i odświeżać je w tle w określonych odstępach czasu.
:::

W przypadku przekroczenia limitu zapytanie do API zwróci status `HTTP 429 - Too Many Requests`.

Jeżeli potrzebujesz zwiększenia swojego limitu API lub chcesz wykorzystać nasze dane w projekcie komercyjnym, [skontaktuj się z nami](https://airly.eu/pl/contact/).

### Nagłówki RateLimit

Każda odpowiedź z API zawiera dodatkowe nagłówki informujące o limitach obowiązujących używany klucz API oraz o ich aktualnym użyciu. Nazwy nagłówków zaczynają się od `X-RateLimit-Limit-` oraz `X-RateLimit-Remaining-`, np.:
```
X-RateLimit-Limit-day: 1000
X-RateLimit-Limit-minute: 50
X-RateLimit-Remaining-day: 996
X-RateLimit-Remaining-minute: 46
```

^^^
