## Time | general.time

All the time values that occur in the API (both as query parameters and as returned payload fields) are [ISO8601](https://en.wikipedia.org/wiki/ISO_8601) timestamps according to [UTC](https://en.wikipedia.org/wiki/Coordinated_Universal_Time) timezone e.g. `2018-08-24T08:24:48.652Z`.

Average measurements that are calculated for particular period of time (e.g. hourly averages) are returned along with that time period. This period is given as a pair of attributes `fromDateTime` and `tillDateTime` and represents a left-closed and right-open time interval `[fromDateTime, tillDatetime)`.

^^^
