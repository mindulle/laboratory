[dart:io](../../dart-io/dart-io-library){._links-link}

open method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[HttpClientRequest](../httpclientrequest-class)\>
open(

1.  [String](../../dart-core/string-class) method,
2.  [String](../../dart-core/string-class) host,
3.  [int](../../dart-core/int-class) port,
4.  [String](../../dart-core/string-class) path

)
:::

Opens a HTTP connection.

The HTTP method to use is specified in `method`, the server is specified
using `host` and `port`, and the path (including a possible query) is
specified using `path`. The path may also contain a URI fragment, which
will be ignored.

The `Host` header for the request will be set to the value `host`:`port`
(if `host` is an IP address, it will still be used in the `Host`
header). This can be overridden through the `HttpClientRequest`
interface before the request is sent.

For additional information on the sequence of events during an HTTP
transaction, and the objects returned by the futures, see the overall
documentation for the class [HttpClient](../httpclient-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<HttpClientRequest> open(
    String method, String host, int port, String path);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/open.html>
:::
