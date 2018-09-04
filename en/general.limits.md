## Terms of use and limits | general.limits

### Terms of use

On a free plan, API consumer is required to use our API only in non-commercial projects.

When presenting data obtained from our API you should present our [logo](https://airly.eu/wp-content/themes/draftweb/images/presskit/big/logo1.jpg).

More details are available in our [Terms of Service](https://airly.eu/docs/tos-en.pdf).

### Limits

In order to maintain high API throughput, availability and quality of the service the API access is rate-limited.

Default rate limits per `apikey` are **1000** API requests per day and **50** API requests per minute for all users.

::: tip
The default limits allow you e.g. to query measurements of particular sensor every 1.5 minute for the whole day or you can query measurements of 40 sensors every hour for the whole day. This should be sufficient for most of the individual use cases.

In case of applications displaying data continuously we recommend caching API responses in local storage and refreshing them periodically.
:::

In case of exceeding the limit API request will return `HTTP 429 - Too Many Requests`.

If you need an increased limit or want to use our data in a commercial project please [contact us](https://airly.eu/en/contact/).

### RateLimit Headers

Each API response contains additional HTTP headers that inform about current API key limits and their usage. Header names begin with `X-RateLimit-Limit-` and  `X-RateLimit-Remaining-`.

```
X-RateLimit-Limit-day: 1000
X-RateLimit-Limit-minute: 50
X-RateLimit-Remaining-day: 996
X-RateLimit-Remaining-minute: 46
```

^^^

