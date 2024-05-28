[dart:io](../../dart-io/dart-io-library){._links-link}

compressionState property
=========================

::: {#getter .section .multi-line-signature}
[HttpClientResponseCompressionState](../httpclientresponsecompressionstate)
compressionState

::: {.features}
\@Since(\"2.4\")
:::
:::

The compression state of the response.

This specifies whether the response bytes were compressed when they were
received across the wire and whether callers will receive compressed or
uncompressed bytes when they listed to this response\'s byte stream.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.4")
HttpClientResponseCompressionState get compressionState;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponse/compressionState.html>
:::
