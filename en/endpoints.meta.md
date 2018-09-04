## Meta | endpoints.meta

Some data types in the API have dynamic nature and their values and ranges can change over time. E.g. in the future our API may support new measurement types (e.g. gases) or new index types used in different countries. Operations in group `/v2/meta` return information about current types and values supported by the API.

::: tip
With meta operations, you can build more dynamic applications and user interfaces that adapt on the fly to the data returned by the API. For example, on our map a colorful legend describing index levels is created thanks to the meta operation.
:::

^^^
