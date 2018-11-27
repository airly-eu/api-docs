## Instalacje | endpoints.installations

Operacje z grupy `/v2/installations/` umożliwiają wyszukiwanie instalacji oraz pobieranie ich metadanych takich jak położenie, dane adresowe itd. Wszystkie operacje zwracają jednolity format odpowiedzi, której poszczególne pola oznaczają:
- **id** (_integer_) - unikalny identyfikator instalacji;  za pomocą id można odpytywać o pomiary konkretnej instalacji
- **latitude**, **longitude** (_double_) -  współrzędne geograficzne instalacji; określają dokładne położenie czujnika na mapie
- **address**:
    - **country**, **city**, **street**, **number** (_string_) -  dane adresowe instalacji; każde z pól opcjonalne, może być puste
    - **displayAddress1**, **displayAddress2** (_string_) -  dodatkowe informacje dot. lokalizacji np. nazwa szkoły lub przedszkola; pola opcjonalne
- **elevation** (_double_) -  określa wysokość w metrach nad poziomem morza na jakiej zamontowany jest sensor
- **airly** (_bool_) -  flaga określająca czy instalacja jest urządzeniem Airly; np. stacje pomiarowe GIOŚ są oznaczone jako false
- **sponsor**:
    - **id** (_integer_) - identyfikator sponsora instalacji
    - **name** (_string_) -  nazwa sponsora instalacji
    - **description** (_string_) -  dodatkowy tekst opisujący sponsora instalacji, pole opcjonalne
    - **logo** (_string_) -  adres url prowadzący do logo sponsora (obrazek w formacie jpg); pole opcjonalne
    - **link** (_string_) -  adres url prowadzący do strony www sponsora; pole opcjonalne

^^^

### Przykład obiektu Installation

```json
{
  "id": 204,
  "location": {
    "latitude": 50.062006,
    "longitude": 19.940984
  },
  "address": {
    "country": "Poland",
    "city": "Kraków",
    "street": "Mikołajska",
    "number": "4B",
    "displayAddress1": "Kraków",
    "displayAddress2": "Mikołajska"
  },
  "elevation": 220.38,
  "airly": true,
  "sponsor": {
    "name": "KrakówOddycha",
    "description": "Sensor Airly w ramach akcji",
    "logo": "https://cdn.airly.eu/logo/KrakówOddycha.jpg",
    "link": "https://przykladowy_link_do_strony_sponsora.pl"
  }
}
```
