[dart:io](../../dart-io/dart-io-library){._links-link}

put method
==========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[HttpClientRequest](../httpclientrequest-class)\>
put(

1.  [String](../../dart-core/string-class) host,
2.  [int](../../dart-core/int-class) port,
3.  [String](../../dart-core/string-class) path

)
:::

Opens a HTTP connection using the PUT method.

The server is specified using `host` and `port`, and the path (including
a possible query) is specified using `path`.

See [open](open) for details.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<HttpClientRequest> put(String host, int port, String path);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/put.html>
:::
