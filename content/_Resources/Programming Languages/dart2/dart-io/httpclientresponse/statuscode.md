[dart:io](../../dart-io/dart-io-library){._links-link}

statusCode property
===================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) statusCode
:::

Returns the status code.

The status code must be set before the body is written to. Setting the
status code after writing to the body will throw a `StateError`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get statusCode;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponse/statusCode.html>
:::
