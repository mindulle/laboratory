[dart:io](../../dart-io/dart-io-library){._links-link}

startConnect method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[ConnectionTask](../connectiontask-class)\<[Socket](../socket-class)\>\>
startConnect(

1.  dynamic host,
2.  [int](../../dart-core/int-class) port,
3.  {dynamic sourceAddress,
4.  [int](../../dart-core/int-class) sourcePort = 0}

)
:::

Like [connect](connect), but returns a
[Future](../../dart-async/future-class) that completes with a
`ConnectionTask` that can be cancelled if the [Socket](../socket-class)
is no longer needed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<ConnectionTask<Socket>> startConnect(host, int port,
    {sourceAddress, int sourcePort = 0}) {
  final IOOverrides? overrides = IOOverrides.current;
  if (overrides == null) {
    return Socket._startConnect(host, port,
        sourceAddress: sourceAddress, sourcePort: sourcePort);
  }
  return overrides.socketStartConnect(host, port,
      sourceAddress: sourceAddress, sourcePort: sourcePort);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Socket/startConnect.html>
:::
