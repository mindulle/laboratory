[dart:io](../../dart-io/dart-io-library){._links-link}

close method
============

::: {.section .multi-line-signature}
void close(

1.  {[bool](../../dart-core/bool-class) force = false}

)
:::

Shuts down the HTTP client.

If `force` is `false` (the default) the
[HttpClient](../httpclient-class) will be kept alive until all active
connections are done. If `force` is `true` any active connections will
be closed to immediately release all resources. These closed connections
will receive an error event to indicate that the client was shut down.
In both cases trying to establish a new connection after calling
[close](close) will throw an exception.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void close({bool force = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/close.html>
:::
