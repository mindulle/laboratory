[dart:io](../../dart-io/dart-io-library){._links-link}

defaultResponseHeaders property
===============================

::: {#getter .section .multi-line-signature}
[HttpHeaders](../httpheaders-class) defaultResponseHeaders
:::

Default set of headers added to all response objects.

By default the following headers are in this set:

``` {.language-dart data-language="dart"}
Content-Type: text/plain; charset=utf-8
X-Frame-Options: SAMEORIGIN
X-Content-Type-Options: nosniff
X-XSS-Protection: 1; mode=block
```

If the `Server` header is added here and the `serverHeader` is set as
well then the value of `serverHeader` takes precedence.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
HttpHeaders get defaultResponseHeaders;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpServer/defaultResponseHeaders.html>
:::
