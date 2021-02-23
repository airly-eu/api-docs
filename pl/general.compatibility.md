## Kompatybilność | general.compatibility

Na ile to tylko możliwe, niniejsze API będzie rozwijane z zachowaniem kompatybilności wstecznej.

Odpowiedzi JSON mają następujące cechy gwarantujące stabilność API:

- Pola obiektów JSON zawsze zachowują swoją nazwę oraz typ wartości
- Pola oznaczone jako obowiązkowe zawsze będą zwracane w odpowiedzi i nigdy nie zostaną usunięte z API
- Pola oznaczone jako opcjonalne mogą ale nie muszą być zwrócone przez API, i jako takie mogą również być usunięte z API całkowicie
- Struktury dynamiczne, takie jak listy i mapy mogą zawierać dowolną liczbę elementów; w szczególności mogą być puste
- Nowe pola mogą być dodane do odpowiedzi API w dowolnym momencie. Nie będą one kolidować z istniejącymi polami ani zmieniać ich znaczenia

::: tip
W praktyce powyższe zasady oznaczają, że pola obowiązkowe zawsze będą w odpowiedzi i nie ma potrzeby sprawdzania ich obecności. Pola opcjonalne należy zawsze sprawdzać pod kątem obecności a ich brak lub wartość null należy stosownie obsłużyć. Nie należy oczekiwać, że listy bądź mapy będą zawierać jakieś określone spodziewane wartości, bądź konkretną liczbę elementów.

Np. instalacja która z jakiegoś powodu mierzy tylko wartości pogodowe (np. sensor pyłów jest uszkodzony), w polu `values` nie zwróci wartości pyłów PM.

Korzystając z bibliotek do parsowania JSON należy skonfigurować je tak, by ignorowały nowe, nieznane pola, ponieważ wraz z rozwojem API możemy dodawać nowe pola do odpowiedzi bez uprzedzenia.
:::

Jeżeli zajdzie konieczność zmiany jakichś operacji lub modeli odpowiedzi w sposób niekompatybilny wstecz, wówczas utworzona zostanie nowa operacja API z nowym modelem odpowiedzi. Będziemy utrzymywać zarówno starą jak i nową operację do czasu aż stara operacja będzie mogła być w sposób bezpieczny wycofana i usunięta. Jeśli taka sytuacja zajdzie poinformujemy użytkowników API.

Zachowanie interfejsu API może ulec zmianie bez ostrzeżenia, jeśli istniejące zachowanie jest nieprawidłowe lub stanowi lukę w zabezpieczeniach.

^^^
