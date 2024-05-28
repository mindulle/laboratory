[dart:io](../../dart-io/dart-io-library){._links-link}

contentLength property
======================

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) contentLength
:::

Returns the content length of the response body. Returns -1 if the size
of the response body is not known in advance.

If the content length needs to be set, it must be set before the body is
written to. Setting the content length after writing to the body will
throw a `StateError`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get contentLength;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponse/contentLength.html>
:::
