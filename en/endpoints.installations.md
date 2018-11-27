## Installations | endpoints.installations

Operations in group `/v2/installations/` allow to search and list available installations and retrieve their metadata, e.g. location, address data etc. All the operations return unified payload response with following attributes:
- **id** (_integer_) - unique installation identifier; having installationId you can query measurements from particular installation
- **latitude**, **longitude** (_double_) - installation coordinates; exact sensor location on map
- **address**:
    - **country**, **city**, **street**, **number** (_string_) - installation address data; each attribute is optional, may be empty or null
    - **displayAddress1**, **displayAddress2** (_string_) - extra fields describing address, e.g. school name or number; optional fields
- **elevation** (_double_) - altitude at which device is installed; meters above mean sea level ([mamsl](https://en.wikipedia.org/wiki/Metres_above_sea_level))
- **airly** (_bool_) - flag indicating whether this installation is an Airly device or not; e.g. GIOŚ stations are flagged as false
- **sponsor**:
    - **id** (_integer_) - sponsor identifier
    - **name** (_string_) - name of this installation's sponsor
    - **description** (_string_) - additional description of this installation's sponsor; optional field
    - **logo** (_string_) - url pointing to sponsor's logo (jpg image); optional field
    - **link** (_string_) - url pointing to sponsor's website; optional field

^^^

### Example Installation

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
    "description": "Airly Sensor is part of action",
    "logo": "https://cdn.airly.eu/logo/KrakówOddycha.jpg",
    "link": "https://sponsor_home_address.pl"
  }
}
```
