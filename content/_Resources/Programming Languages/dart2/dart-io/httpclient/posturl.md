[dart:io](../../dart-io/dart-io-library){._links-link}

postUrl method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[HttpClientRequest](../httpclientrequest-class)\>
postUrl(

1.  [Uri](../../dart-core/uri-class) url

)
:::

Opens a HTTP connection using the POST method.

The URL to use is specified in `url`.

See [openUrl](openurl) for details.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<HttpClientRequest> postUrl(Uri url);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/postUrl.html>
:::
