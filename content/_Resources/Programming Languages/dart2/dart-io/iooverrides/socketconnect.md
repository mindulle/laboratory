[dart:io](../../dart-io/dart-io-library){._links-link}

socketConnect method
====================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Socket](../socket-class)\>
socketConnect(

1.  dynamic host,
2.  [int](../../dart-core/int-class) port,
3.  {dynamic sourceAddress,
4.  [int](../../dart-core/int-class) sourcePort = 0,
5.  [Duration](../../dart-core/duration-class)? timeout}

)
:::

Asynchronously returns a `Socket` connected to the given host and port.

When this override is installed, this functions overrides the behavior
of `Socket.connect(...)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Socket> socketConnect(host, int port,
    {sourceAddress, int sourcePort = 0, Duration? timeout}) {
  return Socket._connect(host, port,
      sourceAddress: sourceAddress, sourcePort: sourcePort, timeout: timeout);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/socketConnect.html>
:::
