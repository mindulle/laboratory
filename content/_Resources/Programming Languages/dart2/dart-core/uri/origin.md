[dart:core](../../dart-core/dart-core-library){._links-link}

origin property
===============

::: {#getter .section .multi-line-signature}
[String](../string-class) origin
:::

Returns the origin of the URI in the form scheme://host:port for the
schemes http and https.

It is an error if the scheme is not \"http\" or \"https\", or if the
host name is missing or empty.

See: <https://www.w3.org/TR/2011/WD-html5-20110405/origin-0.html#origin>

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get origin;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/origin.html>
:::
