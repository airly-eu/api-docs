## Pomiary | concepts.measurements

Wszystkie operacje zaczynające się od `/v2/measurements/` zwracają ujednolicony format odpowiedzi zawierający dane pomiarowe z danej instalacji lub wybranego obszaru (w zależności od parametrów operacji). Każda odpowiedź zawiera pola:
- `current` - są to dane pomiarowe z ostatniej godziny (średnia krocząca z ostatnich 60 minut)
- `history` - pomiary historyczne, obecnie 24 ostatnie pełne godziny zawierające średnie pomiary godzinowe, posortowane rosnąco
- `forecast` - prognoza pomiarów, obecnie 24 nadchodzące godziny zawierające przewidywane średnie pomiary godzinowe, posortowane rosnąco

W każdym z powyższych pól znajdziemy zarówno surowe wartości pomiarowe, jak i wyliczone z nich wartości indeksów oraz ewentualne przekroczenia standardów jakości powietrza.

W przypadku prezentowania w swoich aplikacjach danych pochodzących bezpośrednio z API lub będących efektem ich przetworzenia (np. wyliczenie innego indeksu) zalecane jest w jasny i czytelny sposób podkreślanie co dane wartości oznaczają.

^^^
