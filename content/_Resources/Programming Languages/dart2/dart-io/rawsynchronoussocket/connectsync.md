[dart:io](../../dart-io/dart-io-library){._links-link}

connectSync method
==================

::: {.section .multi-line-signature}
[RawSynchronousSocket](../rawsynchronoussocket-class) connectSync(

1.  dynamic host,
2.  [int](../../dart-core/int-class) port

)
:::

Creates a new socket connection and returns a
[RawSynchronousSocket](../rawsynchronoussocket-class).

The `host` can either be a [String](../../dart-core/string-class) or an
[InternetAddress](../internetaddress-class). If `host` is a
[String](../../dart-core/string-class), [connectSync](connectsync) will
perform a [InternetAddress.lookup](../internetaddress/lookup) and try
all returned [InternetAddress](../internetaddress-class)es, until
connected. Unless a connection was established, the error from the first
failing connection is returned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static RawSynchronousSocket connectSync(host, int port);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSynchronousSocket/connectSync.html>
:::
