### GET /v2/meta/indexes | endpoints.meta.indexes

Endpoint returns a list of all the index types supported in the API along with lists of levels defined per each index type.

The returned array contains objects of type _IndexType_, which contain following fields:
- **name** (_string_) - name of this index type, e.g. AIRLY_CAQI
- **levels** - list of index levels definitions; contains objects of type _IndexLevel_:
    - **values** (_string_) - range of index values that this level represents, e.g. 0-25
    - **level** (_string_) - name of this index level e.g. "VERY_LOW"
    - **description** (_string_) - description of this index level; e.g. "Very Low"; this is a translated field, the value is returned in a language according to `Accept-Language` request header
    - **color** (_string_) - color representation of this index level, given by hexadecimal RGB triplet (e.g. #6BC926)

^^^

### Example request:

```bash
curl -X GET \
    --header 'Accept: application/json' \
    --header 'apikey: {{ apikey }}' \
    'https://airapi.airly.eu/v2/meta/indexes'
```

### Example response

```json
[
  {
    "name": "AIRLY_CAQI",
    "levels": [
      {
        "values": "0-25",
        "level": "VERY_LOW",
        "description": "Very Low",
        "color": "#6BC926"
      },
      ...
    ]
  },
  ...
]
```
