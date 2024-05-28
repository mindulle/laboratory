[dart:io](../../dart-io/dart-io-library){._links-link}

redirect method
===============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[HttpClientResponse](../httpclientresponse-class)\>
redirect(

1.  \[[String](../../dart-core/string-class)? method,
2.  [Uri](../../dart-core/uri-class)? url,
3.  [bool](../../dart-core/bool-class)? followLoops\]

)
:::

Redirects this connection to a new URL. The default value for `method`
is the method for the current request. The default value for `url` is
the value of the
[HttpHeaders.locationHeader](../httpheaders/locationheader-constant)
header of the current response. All body data must have been read from
the current response before calling [redirect](redirect).

All headers added to the request will be added to the redirection
request. However, any body sent with the request will not be part of the
redirection request.

If `followLoops` is set to `true`, redirect will follow the redirect,
even if the URL was already visited. The default value is `false`.

The method will ignore
[HttpClientRequest.maxRedirects](../httpclientrequest/maxredirects) and
will always perform the redirect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<HttpClientResponse> redirect(
    [String? method, Uri? url, bool? followLoops]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponse/redirect.html>
:::
