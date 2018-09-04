# Informacje ogólne | general

Airly API oparte jest o koncepcję **REST**. Nasze API udostępnia operacje zorganizowane wokół zasobów (Installations oraz Measurements), które mają intuicyjne i przewidywalne ścieżki URL. Bazujemy na standardowych mechanizmach protokołu HTTP w kwestiach takich jak wykonywanie operacji (metody HTTP) czy obsługa zwracanych błędów (statusy HTTP).

Możliwe jest wywoływanie operacji API z poziomu aplikacji klienckich z innych domen - API wspiera tzw. cross-origin.

Wszystkie operacje zwracają odpowiedzi w formacie **JSON** (w tym także błędy) wraz z nagłówkiem HTTP `Content-Type: application/json`, kodowane zestawem znaków `UTF-8`, chyba, że zaznaczono inaczej w opisie danej operacji.

^^^
