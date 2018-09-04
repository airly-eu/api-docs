## Meta | endpoints.meta

Niektóre typy danych w API mają dynamiczny charakter i ich zakresy mogą zmieniać się w czasie. Np. w przyszłości w API mogą pojawić się nowe typy pomiarów (np. gazy) lub wsparcie dla indeksów z innych państw. Operacje z grupy `/v2/meta` zwracają informacje o tym jakie konkretnie rodzaje danych są aktualnie dostępne w API.

::: tip
Dzięki operacjom meta można budować bardziej dynamiczne aplikacje i interfejsy użytkownika, które dostosowują się w locie do danych zwracanych przez API. Np. na naszej mapie kolorowa legenda opisująca poziomy indeksów tworzona jest właśnie dzięki operacji meta.
:::

^^^
