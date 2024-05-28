[dart:io](../../dart-io/dart-io-library){._links-link}

contentLength property
======================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) contentLength

::: {.features}
read / write
:::
:::

Gets and sets the content length of the request.

If the size of the request is not known in advance set content length to
-1, which is also the default.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int contentLength = -1;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientRequest/contentLength.html>
:::
