## Language | general.language

Some API endpoints return textual content, e.g. description of current air quality. Such texts are translated and returned in a language according to user preference.

To select API content language you should include an `Accept-Language` HTTP header in your request with value set to desired language.

Currently supported languages are English ("en" - default) and Polish ("pl").

^^^
