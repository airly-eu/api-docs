## Installations | concepts.installations

In the previous API version we were dealing with a concept of a sensor. You could e.g. query what sensors are present in a given area, and then query each individual sensor for its measurements by the sensorId. Unfortunately such approach can lead to some problems. Our devices fleet is constantly growing and it is inevitable that at some point particular device will have to be replaced or moved to another location. When that happens, querying for data by sensorId can lead to incorrect results, since you would be querying for a device that was in fact removed, or replaced.

In the new API version we solve this problem by introducing a concept of **installation**. An installation is an entity that binds together a sensor and its location where it's installed at a particular time. Thus you can always query an installation safely without risking you would be querying incorrect sensor.

In case a sensor is removed from its location, future queries for its installation can result in either:
- if the sensor was replaced with another one, queries will result in HTTP `301 Moved Permanently` with `Location` header pointing to a new url you should query. In addition, a JSON payload is returned:

```json
{
    "errorCode": "INSTALLATION_REPLACED",
    "message": "Installation was replaced with another one",
    "details": {
        "successorId": &lt;new installation identifier&gt;
    }
}
```

- if there is no replacement sensor in the same location (no "successorId") then queries will result in `404 Not Found`

In principle we recommend using other API endpoints, e.g. those that return measurements by location, or those that return average measurements for a wider area. Then you don't heave to bother with installations, IDs, etc. However, if you still need to query particular installation, just keep in mind the above rules and handle returned codes properly.

^^^
