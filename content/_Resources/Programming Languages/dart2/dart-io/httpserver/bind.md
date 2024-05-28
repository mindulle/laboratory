[dart:io](../../dart-io/dart-io-library){._links-link}

bind method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[HttpServer](../httpserver-class)\>
bind(

1.  dynamic address,
2.  [int](../../dart-core/int-class) port,
3.  {[int](../../dart-core/int-class) backlog = 0,
4.  [bool](../../dart-core/bool-class) v6Only = false,
5.  [bool](../../dart-core/bool-class) shared = false}

)
:::

Starts listening for HTTP requests on the specified `address` and
`port`.

The `address` can either be a [String](../../dart-core/string-class) or
an [InternetAddress](../internetaddress-class). If `address` is a
[String](../../dart-core/string-class), [bind](bind) will perform a
[InternetAddress.lookup](../internetaddress/lookup) and use the first
value in the list. To listen on the loopback adapter, which will allow
only incoming connections from the local host, use the value
[InternetAddress.loopbackIPv4](../internetaddress/loopbackipv4) or
[InternetAddress.loopbackIPv6](../internetaddress/loopbackipv6). To
allow for incoming connection from the network use either one of the
values [InternetAddress.anyIPv4](../internetaddress/anyipv4) or
[InternetAddress.anyIPv6](../internetaddress/anyipv6) to bind to all
interfaces or the IP address of a specific interface.

If an IP version 6 (IPv6) address is used, both IP version 6 (IPv6) and
version 4 (IPv4) connections will be accepted. To restrict this to
version 6 (IPv6) only, use `v6Only` to set version 6 only. However, if
the address is
[InternetAddress.loopbackIPv6](../internetaddress/loopbackipv6), only IP
version 6 (IPv6) connections will be accepted.

If `port` has the value 0 an ephemeral port will be chosen by the
system. The actual port used can be retrieved using the `port` getter.

The optional argument `backlog` can be used to specify the listen
backlog for the underlying OS listen setup. If `backlog` has the value
of 0 (the default) a reasonable value will be chosen by the system.

The optional argument `shared` specifies whether additional `HttpServer`
objects can bind to the same combination of `address`, `port` and
`v6Only`. If `shared` is `true` and more `HttpServer`s from this isolate
or other isolates are bound to the port, then the incoming connections
will be distributed among all the bound `HttpServer`s. Connections can
be distributed over multiple isolates this way.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<HttpServer> bind(address, int port,
        {int backlog = 0, bool v6Only = false, bool shared = false}) =>
    _HttpServer.bind(address, port, backlog, v6Only, shared);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpServer/bind.html>
:::
