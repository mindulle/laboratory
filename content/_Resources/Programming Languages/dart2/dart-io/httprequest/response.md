[dart:io](../../dart-io/dart-io-library){._links-link}

response property
=================

::: {#getter .section .multi-line-signature}
[HttpResponse](../httpresponse-class) response
:::

The [HttpResponse](../httpresponse-class) object, used for sending back
the response to the client.

If the [contentLength](contentlength) of the body isn\'t 0, and the body
isn\'t being read, any write calls on the
[HttpResponse](../httpresponse-class) automatically drain the request
body.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
HttpResponse get response;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpRequest/response.html>
:::
