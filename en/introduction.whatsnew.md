## What's new in API 2.0 | introduction.whatsnew

This documentation applies to API version 2.0. Comparing to previous version we are happy to announce lots of improvements:

- "Sensors" have been replaced in the API with ["Installations"](#concepts.installations).
- We added support for various types of [indexes](#concepts.indexes) and air quality [standards](#concepts.standards).
- We added simpler and more intuitive [API Endpoints](#endpoints). We have simplified and unified response models. We added better request validation and error handling. We have removed some unsupported / not working query parameters and redundant or non-intuitive endpoints.
- The API returns now more details about installation ["Sponsor"](#concepts.installations.sponsors).
- The API returns now better [installation address](#endpoints.installations) data and the altitude at which the sensor is installed.
- The API returns now [color](#endpoints.measurements) representing pollution level and additional text describing particular air quality index.
- The API returns now [measurement units](#endpoints.meta.measurements) and supported types of measurements.
- The API returns now texts translated to [multiple languages](#general.language).

## API 1.0 support | introduction.whatsnew.apiv1support

Unfortunately it is not possible for us to maintain two versions of the API in parallel for an extended period of time. We therefore propose the following plan to fade out and eventually drop the current version:
- For the next 3 months we will fully support both API versions. This is a good moment to start migrating over to version 2.0
- After **30.11.2018** we will stop adding new sensor installations to the old API version. The API will continue to operate and return measurements, but only for the sensors installed before that date. This will allow the existing applications that have not yet migrated to continue working, however to get access to most recent data they will have to switch to newer version.
- After **28.02.2019** the support for API 1.0 will be dropped.

We are convinced that the proposed dates give you enough time to make the necessary changes in your applications.

The specification of the previous version of the API is available [here](/api).

^^^
