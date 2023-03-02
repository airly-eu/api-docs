## Locations | concepts.installations.locations

Location consists of unique location id, latitude, longitude and descriptive parameters like street name, city, country etc.
Every installation is binded to a location wherein every location can be associated with at most 1 installation, there might be multiple installations in the same location if their intervals of functioning don't overlap.

API allows to build queries based on location id instead of installation id, these queries return data from all the historical installations in the location, so you don't have to worry about reinstalled devices.

^^^
