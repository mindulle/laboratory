[dart:io](../../dart-io/dart-io-library){._links-link}

bind method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RawDatagramSocket](../rawdatagramsocket-class)\>
bind(

1.  dynamic host,
2.  [int](../../dart-core/int-class) port,
3.  {[bool](../../dart-core/bool-class) reuseAddress = true,
4.  [bool](../../dart-core/bool-class) reusePort = false,
5.  [int](../../dart-core/int-class) ttl = 1}

)
:::

Binds a socket to the given `host` and `port`.

When the socket is bound and has started listening on `port`, the
returned future completes with the `RawDatagramSocket` of the bound
socket.

The `host` can either be a [String](../../dart-core/string-class) or an
[InternetAddress](../internetaddress-class). If `host` is a
[String](../../dart-core/string-class), [bind](bind) will perform a
[InternetAddress.lookup](../internetaddress/lookup) and use the first
value in the list. To listen on the loopback interface, which will allow
only incoming connections from the local host, use the value
[InternetAddress.loopbackIPv4](../internetaddress/loopbackipv4) or
[InternetAddress.loopbackIPv6](../internetaddress/loopbackipv6). To
allow for incoming connection from any network use either one of the
values [InternetAddress.anyIPv4](../internetaddress/anyipv4) or
[InternetAddress.anyIPv6](../internetaddress/anyipv6) to bind to all
interfaces, or use the IP address of a specific interface.

The `reuseAddress` should be set for all listeners that bind to the same
address. Otherwise, it will fail with a
[SocketException](../socketexception-class).

The `reusePort` specifies whether the port can be reused.

The `ttl` sets `time to live` of a datagram sent on the socket.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static Future<RawDatagramSocket> bind(host, int port,
    {bool reuseAddress = true, bool reusePort = false, int ttl = 1});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawDatagramSocket/bind.html>
:::
