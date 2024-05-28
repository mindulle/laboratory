[dart:io](../../dart-io/dart-io-library){._links-link}

name property
=============

::: {#getter .section .multi-line-signature}
[String](../../dart-core/string-class) name
:::

Get the name of the type, e.g. \"IPv4\" or \"IPv6\".

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String get name => const ["ANY", "IPv4", "IPv6", "Unix"][_value + 1];
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/InternetAddressType/name.html>
:::
