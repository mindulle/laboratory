[dart:io](../../dart-io/dart-io-library){._links-link}

autoCompress property
=====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) autoCompress

::: {.features}
read / write
:::
:::

Whether the [HttpServer](../httpserver-class) should compress the
content, if possible.

The content can only be compressed when the response is using chunked
Transfer-Encoding and the incoming request has `gzip` as an accepted
encoding in the Accept-Encoding header.

The default value is `false` (compression disabled). To enable, set
`autoCompress` to `true`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool autoCompress = false;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpServer/autoCompress.html>
:::
