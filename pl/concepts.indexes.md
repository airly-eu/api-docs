## Indeksy | concepts.indexes

Indeks jakości powietrza to sposób przeliczenia surowych danych pomiarowych dla różnych zanieczyszczeń (np. pyłów, gazów itp.) na jedną wartość reprezentującą stopień zanieczyszczenia powietrza. Indeksom jakości powietrza zazwyczaj towarzyszy wartość liczbowa z arbitralnie dobranej skali (np. 0-100), skwantowany poziom zanieczyszczeń (np. "Niski", "Wysoki"), kolor reprezentujący dany poziom zanieczyszczenia (np. zielony, czerwony) a czasem także dodatkowe wartości opisowe, jak np. ostrzeżenie o skutkach zdrowotnych jakie niesie dane zanieczyszczenie.

Celem indeksu jakości powietrza jest prezentowanie danych o poziomie zanieczyszczeń w sposób prosty, przejrzysty i zrozumiały dla ogółu społeczeństwa, w szczególności przez osoby które nie są zaznajomione z obowiązującymi normami i np. nie wiedzą jakie wartości pyłu PM10 w powietrzu są bezpieczne a jakie niebezpieczne dla zdrowia. Po drugie indeks sprowadza dane dla różnych składników zanieczyszczeń (np. pyły, gazy) do jednej wartości i reprezentuje ujednolicony (i nieco uproszczony) obraz jakości powietrza w danym miejscu, niezależnie od tego, który czynnik zanieczyszczający powietrze dominuje na danym terenie.

Indeksy jakości powietrza tworzone są przez krajowe i międzynarodowe organizacje zajmujące się ochroną środowiska. Istnieją różne indeksy stosowane w różnych krajach. Np. w Unii Europejskiej szeroko stosowany jest [indeks CAQI](https://www.airqualitynow.eu/pl/about_indices_definition.php) przygotowany w ramach projektu CITEAIR. W Polsce dodatkowo stosowany jest [Polski Indeks Jakości Powietrza](http://powietrze.gios.gov.pl/pjp/content/show/1001197) (PIJP) zdefiniowany i wyliczany przez Główny Inspektorat Ochrony Środowiska. Ponieważ różne indeksy mają różny sposób obliczania, ten same dane pomiarowe na danym terenie mogą być interpretowane jako różne wartości indeksów, różne poziomy zanieczyszczeń i być reprezentowane przez różne kolory.

Platforma Airly wspiera w tej chwili dwa indeksy jakości powietrza: [CAQI](https://www.airqualitynow.eu/pl/about_indices_definition.php), oraz [Polski Indeks Jakości Powietrza - PIJP](http://powietrze.gios.gov.pl/pjp/content/show/1001197). Odpowiedzi API zawierają indeks wyliczony dla danych pomiarowych określony parametrem zapytania `indexType`.

Listę wszystkich indeksów które wspiera platforma oraz definicje ich poziomów i przedziałów wraz z kolorami można uzyskać odpytując adres `/v2/meta/indexes`.

^^^
