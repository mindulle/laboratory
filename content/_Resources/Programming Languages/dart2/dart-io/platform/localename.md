[dart:io](../../dart-io/dart-io-library){._links-link}

localeName property
===================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) localeName
:::

Get the name of the current locale.

The result usually consists of

-   a language (e.g., \"en\"), or
-   a language and country code (e.g. \"en\_US\", \"de\_AT\"), or
-   a language, country code and character set (e.g. \"en\_US.UTF-8\").

On macOS and iOS, the locale is taken from CFLocaleGetIdentifier.

On Linux and Fushia, the locale is taken from the \"LANG\" environment
variable, which may be set to any value. For example:

``` {.language-shell data-language="dart"}
LANG=kitten dart myfile.dart  # localeName is "kitten"
```

On Android, the value will not change while the application is running,
even if the user adjusts their language settings.

See <https://en.wikipedia.org/wiki/Locale_(computer_software)>

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static String get localeName => _Platform.localeName();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Platform/localeName.html>
:::
