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

Since **28.02.2019** the support for API 1.0 has been dropped.

^^^
