[dart:io](../../dart-io/dart-io-library){._links-link}

openUrl method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[HttpClientRequest](../httpclientrequest-class)\>
openUrl(

1.  [String](../../dart-core/string-class) method,
2.  [Uri](../../dart-core/uri-class) url

)
:::

Opens a HTTP connection.

The HTTP method is specified in `method` and the URL to use in `url`.

The `Host` header for the request will be set to the value
[Uri.host](../../dart-core/uri/host):[Uri.port](../../dart-core/uri/port)
from `url` (if `url.host` is an IP address, it will still be used in the
`Host` header). This can be overridden through the `HttpClientRequest`
interface before the request is sent.

For additional information on the sequence of events during an HTTP
transaction, and the objects returned by the futures, see the overall
documentation for the class [HttpClient](../httpclient-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<HttpClientRequest> openUrl(String method, Uri url);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/openUrl.html>
:::
