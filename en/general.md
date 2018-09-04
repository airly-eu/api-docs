# General information | general

Airly API is based on **REST**. Our API has predictable and intuitive URLs, organized around resources (Installations and Measurements). We use built-in HTTP features for issuing requests (HTTP methods) and handling errors (HTTP statuses).

It is possible to interact with our API from a client-side web applications served from a different domain - our API supports cross-origin requests.

All the API endpoints return content in **JSON** format (including errors) along with `Content-Type: application/json` HTTP header encoded using charset `UTF-8`, unless noted otherwise in the endpoint description.

^^^
