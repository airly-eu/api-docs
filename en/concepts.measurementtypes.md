### Measurement types | concepts.measurementtypes

Our devices are capable of measuring various types of measurements: temperature, humidity, atmospheric pressure, particulate matter concentrations etc. Our API also gives access to data from other measurement stations (e.g. [GIOŚ](https://powietrze.gios.gov.pl) stations) which measure only some of these parameters (e.g. only PM10). To provide access to all this data in a unified and standard way, measurement data is returned in a dynamic structure in the form of a list (JSON array). The list elements are "name-value" pairs, each for a particular type of measurement.

A list of all types of measurements supported by the API, their names and units used can be retrieved by querying  `/v2/meta/measurements`.

^^^
