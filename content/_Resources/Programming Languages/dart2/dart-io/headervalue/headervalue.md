[dart:io](../../dart-io/dart-io-library){._links-link}

HeaderValue constructor
=======================

::: {.section .multi-line-signature}
HeaderValue(

1.  \[[String](../../dart-core/string-class) value = \"\",
2.  [Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    [String](../../dart-core/string-class)?\> parameters = const {}\]

)
:::

Creates a new header value object setting the value and parameters.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HeaderValue(
    [String value = "", Map<String, String?> parameters = const {}]) {
  return _HeaderValue(value, parameters);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HeaderValue/HeaderValue.html>
:::
