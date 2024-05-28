[dart:io](../../dart-io/dart-io-library){._links-link}

socketStartConnect method
=========================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[ConnectionTask](../connectiontask-class)\<[Socket](../socket-class)\>\>
socketStartConnect(

1.  dynamic host,
2.  [int](../../dart-core/int-class) port,
3.  {dynamic sourceAddress,
4.  [int](../../dart-core/int-class) sourcePort = 0}

)
:::

Asynchronously returns a `ConnectionTask` that connects to the given
host and port when successful.

When this override is installed, this functions overrides the behavior
of `Socket.startConnect(...)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<ConnectionTask<Socket>> socketStartConnect(host, int port,
    {sourceAddress, int sourcePort = 0}) {
  return Socket._startConnect(host, port,
      sourceAddress: sourceAddress, sourcePort: sourcePort);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/IOOverrides/socketStartConnect.html>
:::
