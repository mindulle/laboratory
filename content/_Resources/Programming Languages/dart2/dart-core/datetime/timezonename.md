[dart:core](../../dart-core/dart-core-library){._links-link}

timeZoneName property
=====================

::: {#getter .section .multi-line-signature}
[String](../string-class) timeZoneName
:::

The time zone name.

This value is provided by the operating system and may be an
abbreviation or a full name.

In the browser or on Unix-like systems commonly returns abbreviations,
such as \"CET\" or \"CEST\". On Windows returns the full name, for
example \"Pacific Standard Time\".

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external String get timeZoneName;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/DateTime/timeZoneName.html>
:::
