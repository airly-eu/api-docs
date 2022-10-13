## Measurements | endpoints.measurements

Operations in group `/v2/measurements` allow to query measurements data by various criteria. All the operations return unified payload format, which contains following fields:
- **current** - single element of type _AveragedValues_; contains averaged measurements for the last 60 minutes (moving average); for installations other than Airly (e.g. GIOŚ) could represent data up to 3 hours old, due to delays in third party data arrival
- **history** - list of elements of type _AveragedValues_; contains a list of historical hourly averaged measurements for the last 24 full hours
- **forecast** - list of elements of type _AveragedValues_; contains a list of anticipated future hourly averaged measurements for the next 24 full hours

::: tip
The field `history` contains data for the **last 24 full hours**, e.g. if current time is 09:27 UTC, then that field will contain 24 elements, starting with hour interval 09:00-10:00 UTC yesterday, and ending with hour interval 08:00-09:00 UTC today.

The field `forecast` contains forecast data for the **next 24 full hours**, where the first hour is the current hour; e.g. if current time is 09:27 UTC, then that field will contain 24 elements, starting with hour interval 09:00-10:00 UTC today, and ending with hour interval 08:00-09:00 UTC tomorrow.

It is worth noting that the history and forecast fields form an uninterrupted sequence of data for 48 hours, of which the first 24 hours are measured values, and the next 24 hours are forecast values.

The field `current` contains averaged measurements for the **last 60 minutes** (moving average), up until "now", i.e. the time of the request. For example, if the current time is 09:27 UTC, this field contains data for the time interval 08:27-09:27 UTC. However, for installations other than Airly (e.g. GIOŚ stations) this field may contain data up to 3 hours old, due to delays in third party data arrival.
:::

**AveragedValues** contains:
- **fromDateTime** / **tillDateTime** (_string_) - ISO8601 timestamp; date and time in UTC; the two fields represent time interval during which the data in this payload was measured and averaged
- **values** - array of objects of type _Value_; single element contains:
    - **name** (_string_) - name (type) of the given measurement; e.g. PM10
    - **value** (_double_) - measured value of the given measurement type; e.g. concentration 25µg/m<sup>3</sup>
- **indexes** - array of objects of type _Index_; single element represents an index value calculated for the measurements in this payload
    - **name**  (_string_) - name of the index (e.g. CAQI, or PIJP)
    - **value** (_double_) - numerical value of the calculated index
    - **level** (_string_) - [discreet level of the index](#endpoints.meta.indexes) (e.g. HIGH, or LOW etc.)
    - **description** (_string_) - description of the index level; the text translated and returned in a language according to `Accept-Language` request header
    - **advice** (_string_) - additional text with advice regarding current index level; the text translated and returned in a language according to `Accept-Language` request header
    - **color** (_string_) - color representing index level; in a form of hexadecimal RGB triplet (e.g. #D1CF1E)
- **standards** - array of objects of type _Standard_; single element represents particular air quality standard
    - **name** (_string_) - name of this standard; currently only WHO standards are supported
    - **pollutant** (_string_) - name of the pollutant to which this standard applies, currently only PM10 and PM25 are supported
    - **limit** (_double_) - certain average concentration level of the pollutant which should not be exceeded over given period of time; in other words, this is the value for which the pollutant concentration reaches 100% of the limit
    - **percent** (_double_) - concentration value of a given pollutant expressed as a percentage of this concentration in the standard / limit; e.g. for a standard of 50μg/m<sup>3</sup> of PM10 the concentration of 25μg/m<sup>3</sup> is expressed as 50%

<p>&nbsp;</p>

Query parameters common for all endpoints:
- **indexType** - selects the type of the index which should be calculated and returned in response; currently supported values are AIRLY_CAQI (default), CAQI, and PIJP; (in current API version only 1 selected index is returned)
- **indexPollutant** - selects the set of pollutant types considered when calculating value of the index; currently supported values are PM (default = {PM10, PM25}), PM10, PM25, O3, NO2, SO2, CO, ALL (set of all given pollutants)

^^^

### Example Measurements

```json
{
  "current": {
    "fromDateTime": "2018-08-24T08:24:48.652Z",
    "tillDateTime": "2018-08-24T09:24:48.652Z",
    "values": [
      { "name": "PM1",          "value": 12.73   },
      { "name": "PM25",         "value": 18.7    },
      { "name": "PM10",         "value": 35.53   },
      { "name": "PRESSURE",     "value": 1012.62 },
      { "name": "HUMIDITY",     "value": 66.44   },
      { "name": "TEMPERATURE",  "value": 24.71   },
      ...
    ],
    "indexes": [
      {
        "name": "AIRLY_CAQI",
        "value": 35.53,
        "level": "LOW",
        "description": "Dobre powietrze.",
        "advice": "Możesz bez obaw wyjść na zewnątrz.",
        "color": "#D1CF1E"
      }
    ],
    "standards": [
      {
        "name": "WHO",
        "pollutant": "PM25",
        "limit": 25,
        "percent": 74.81
      },
      ...
    ]
  },
  "history": [ ... ],
  "forecast": [ ... ]
}
```
