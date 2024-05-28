[dart:io](../../dart-io/dart-io-library){._links-link}

reasonPhrase property
=====================

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) reasonPhrase
:::

Returns the reason phrase associated with the status code.

The reason phrase must be set before the body is written to. Setting the
reason phrase after writing to the body will throw a `StateError`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get reasonPhrase;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponse/reasonPhrase.html>
:::
