## Co nowego w API 2.0 | introduction.whatsnew

Niniejsza dokumentacja dotyczy API w wersji 2.0. W stosunku do poprzedniej wersji wprowadziliśmy liczne zmiany i usprawnienia:

- "Sensory" zostały zastąpione w API przez ["Instalacje"](#concepts.installations).
- Wprowadziliśmy wsparcie dla różnych [indeksów](#concepts.indexes) oraz [standardów](#concepts.standards) jakości powietrza.
- Wprowadziliśmy w API prostsze w użyciu, bardziej intuicyjne [operacje](#endpoints). Uprościliśmy i ujednoliciliśmy modele odpowiedzi. Dodaliśmy lepszą walidację zapytań i obsługę błędów. Usunęliśmy nieobsługiwane / niedziałające parametry i redundantne albo nieintuicyjne operacje.
- Zwracamy w API więcej szczegółów nt. ["Sponsora"](#concepts.installations.sponsors) instalacji.
- Zwracamy w API dokładniejsze dane nt. adresu [instalacji](#endpoints.installations) oraz wysokość nad poziomem morza na jakiej zamontowany jest sensor.
- Zwracamy w API [kolor](#endpoints.measurements) reprezentujący poziom zanieczyszczeń oraz dodatkowe teksty dotyczące danego indeksu jakości powietrza.
- Zwracamy w API [jednostki](#endpoints.meta.measurements) oraz typy pomiarów które wspieramy.
- Zwracamy w API teksty w [różnych językach](#general.language).

## Wsparcie dla API 1.0 | introduction.whatsnew.apiv1support

Z dniem **28.02.2019** zakończyliśmy wsparcie starej wersji API 1.0.

^^^
