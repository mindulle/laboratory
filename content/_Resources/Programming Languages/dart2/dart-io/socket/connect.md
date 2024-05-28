[dart:io](../../dart-io/dart-io-library){._links-link}

connect method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Socket](../socket-class)\>
connect(

1.  dynamic host,
2.  [int](../../dart-core/int-class) port,
3.  {dynamic sourceAddress,
4.  [int](../../dart-core/int-class) sourcePort = 0,
5.  [Duration](../../dart-core/duration-class)? timeout}

)
:::

Creates a new socket connection to the host and port and returns a
[Future](../../dart-async/future-class) that will complete with either a
`Socket` once connected or an error if the host-lookup or connection
failed.

`host` can either be a [String](../../dart-core/string-class) or an
[InternetAddress](../internetaddress-class). If `host` is a
[String](../../dart-core/string-class), [connect](connect) will perform
a [InternetAddress.lookup](../internetaddress/lookup) and try all
returned [InternetAddress](../internetaddress-class)es, until connected.
Unless a connection was established, the error from the first failing
connection is returned.

The argument `sourceAddress` can be used to specify the local address to
bind when making the connection. The `sourceAddress` can either be a
[String](../../dart-core/string-class) or an
[InternetAddress](../internetaddress-class). If a
[String](../../dart-core/string-class) is passed it must hold a numeric
IP address.

The `sourcePort` defines the local port to bind to. If `sourcePort` is
not specified or zero, a port will be chosen.

The argument `timeout` is used to specify the maximum allowed time to
wait for a connection to be established. If `timeout` is longer than the
system level timeout duration, a timeout may occur sooner than specified
in `timeout`. On timeout, a [SocketException](../socketexception-class)
is thrown and all ongoing connection attempts to `host` are cancelled.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<Socket> connect(host, int port,
    {sourceAddress, int sourcePort = 0, Duration? timeout}) {
  final IOOverrides? overrides = IOOverrides.current;
  if (overrides == null) {
    return Socket._connect(host, port,
        sourceAddress: sourceAddress,
        sourcePort: sourcePort,
        timeout: timeout);
  }
  return overrides.socketConnect(host, port,
      sourceAddress: sourceAddress, sourcePort: sourcePort, timeout: timeout);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/Socket/connect.html>
:::
