## Measurements | concepts.measurements

All the API endpoints that begin with a prefix `/v2/measurements` return unified response format that contains measurements from particular installation or area (depending on query parameters). Each response contains fields:
- `current` - these are measurements data for the last hour (moving average over last 60 minutes)
- `history` - these are historical measurements, currently last 24 full hours that contain average hourly measurements, in ascending order
- `forecast` - these are measurements forecasts, currently next 24 full hours that contain average anticipated measurements, in ascending order

Each of those fields contains both raw measurement values, as well as indexes calculated using those measurements, and air quality standards violations (where applicable).

When presenting our data in your application it is recommended to indicate clearly what particular data fields mean to avoid any confusion.

^^^
