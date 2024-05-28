[dart:core](../../dart-core/dart-core-library){._links-link}

scheme property
===============

::: {#getter .section .multi-line-signature}
[String](../string-class) scheme
:::

The scheme component of the URI.

The value is the empty string if there is no scheme component.

A URI scheme is case insensitive. The returned scheme is canonicalized
to lowercase letters.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get scheme;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Uri/scheme.html>
:::
