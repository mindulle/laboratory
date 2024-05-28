[dart:io](../../dart-io/dart-io-library){._links-link}

close method
============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class) close(

1.  {[bool](../../dart-core/bool-class) force = false}

)
:::

Permanently stops this [HttpServer](../httpserver-class) from listening
for new connections. This closes the
[Stream](../../dart-async/stream-class) of
[HttpRequest](../httprequest-class)s with a done event. The returned
future completes when the server is stopped. For a server started using
[bind](bind) or [bindSecure](bindsecure) this means that the port
listened on no longer in use.

If `force` is `true`, active connections will be closed immediately.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future close({bool force = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpServer/close.html>
:::
