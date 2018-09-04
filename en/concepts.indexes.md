## Indexes | concepts.indexes

Air quality index is a way to convert raw measurements data for various pollutants (e.g. dust, gases) into single value representing amount of air pollution. Air quality index usually defines a number from an arbitrary scale (e.g. 0-100), some quantized pollution level (e.g. "Low", "High"), a color representing particular pollution level (e.g. green, red) and sometimes additional text or description e.g. a warning about potential health effects of the pollution.

The goal of air quality index is to present air pollution data in a simple way which is easy to understand by majority of people, especially those unfamiliar with air quality standards and e.g. don't know whether the particular PM10 concentration in the air is safe or not. Secondly, the air quality index reduces data for various pollutants (e.g. dusts, gases) to one value and represents a unified (and somewhat simplified) picture of air quality in a given place, regardless of which air pollutant dominates in a given area.

Air quality indexes are defined by national and international organizations responsible for environmental protection. There exist various indexes in different countries. For example, in the European Union, the [CAQI index](https://www.airqualitynow.eu/pl/about_indices_definition.php) prepared as part of the CITEAIR project is widely used. In Poland, the [Polish Air Quality Index](http://powietrze.gios.gov.pl/pjp/content/show/1001197) (PIJP) is also defined and calculated by the Chief Inspectorate for Environmental Protection (GIOŚ). Because different indexes have different calculation methods, the same measurement data in a given area can be interpreted as different index values, different pollution levels and be represented by different colors.

The Airly platform currently supports two air quality indexes: [CAQI](https://www.airqualitynow.eu/pl/about_indices_definition.php) and [Polish Air Quality Index - PIJP](http://powietrze.gios.gov.pl/pjp/content/show/1001197). The API responses contain the index calculated for the measurement data specified by the `indexType` query parameter.

The list of all indexes supported by the platform and the definitions of their levels and ranges with colors can be obtained by querying the address `/v2/meta/indexes`.

^^^
