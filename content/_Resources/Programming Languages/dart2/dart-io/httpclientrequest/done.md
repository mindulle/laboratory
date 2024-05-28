[dart:io](../../dart-io/dart-io-library){._links-link}

done property
=============

::: {#getter .section .multi-line-signature}
[Future](../../dart-async/future-class)\<[HttpClientResponse](../httpclientresponse-class)\>
done

::: {.features}
override
:::
:::

A `HttpClientResponse` future that will complete once the response is
available.

If an error occurs before the response is available, this future will
complete with an error.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<HttpClientResponse> get done;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientRequest/done.html>
:::
