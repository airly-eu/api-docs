## Compatibility | general.compatibility

Wherever possible, this API will be maintained in a backwards compatible manner.

JSON responses have following stability guarantees:

- Properties of JSON objects will continue to have same name and value type
- Properties marked as mandatory will always be returned and will never be removed from the API
- Properties marked as optional may or may not be returned by the API and as such may be removed from the API permanently
- Dynamic structures like arrays and maps may or may not contain some elements; in particular they may be empty sometimes
- New properties may be added to the responses at any time, but they will not collide with existing properties, nor alter their meaning

::: tip
In practice these rules mean that for properties marked as mandatory you can always expect them and there is no need to check for their presence. Optional properties must always be checked and null or missing values handled properly. Arrays and maps must not be expected to contain specific values, or concrete number of elements.

E.g. an installation that for some reason only measures weather conditions (it may have PM sensor broken) will not return the PM values in its `values` array.

When using JSON parsing libraries it is important to configure them in a way to ignore unknown fields, as we may be extending the API and adding new properties to responses without notice.
:::

If it is necessary to change some operations, or its response models in a way that is not backwards compatible, a new endpoint will be created with new response model. We will then maintain both old and new endpoint for an extended period of time, until the old one is safe to be deprecated and dropped. We will inform you if this ever has to occur.

The behaviour of the API may change without warning if the existing behaviour is incorrect or constitutes a security vulnerability.

^^^
