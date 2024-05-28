[dart:io](../../dart-io/dart-io-library){._links-link}

bind method
===========

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RawSecureServerSocket](../rawsecureserversocket-class)\>
bind(

1.  dynamic address,
2.  [int](../../dart-core/int-class) port,
3.  [SecurityContext](../securitycontext-class)? context,
4.  {[int](../../dart-core/int-class) backlog = 0,
5.  [bool](../../dart-core/bool-class) v6Only = false,
6.  [bool](../../dart-core/bool-class) requestClientCertificate = false,
7.  [bool](../../dart-core/bool-class) requireClientCertificate = false,
8.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>?
    supportedProtocols,
9.  [bool](../../dart-core/bool-class) shared = false}

)
:::

Listens on a provided address and port.

When the returned future completes, the server socket is bound to the
given `address` and `port` and has started listening on it.

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

If `port` has the value `0` an ephemeral port will be chosen by the
system. The actual port used can be retrieved using the `port` getter.

The optional argument `backlog` can be used to specify the listen
backlog for the underlying OS listen setup. If `backlog` has the value
of `0` (the default) a reasonable value will be chosen by the system.

Incoming client connections are promoted to secure connections, using
the server certificate and key set in `context`.

`address` must be given as a numeric address, not a host name.

To request or require that clients authenticate by providing an SSL
(TLS) client certificate, set the optional parameters
requestClientCertificate or requireClientCertificate to true. Require
implies request, so one doesn\'t need to specify both. To check whether
a client certificate was received, check SecureSocket.peerCertificate
after connecting. If no certificate was received, the result will be
null.

`supportedProtocols` is an optional list of protocols (in decreasing
order of preference) to use during the ALPN protocol negotiation with
clients. Example values are \"http/1.1\" or \"h2\". The selected
protocol can be obtained via
[RawSecureSocket.selectedProtocol](../rawsecuresocket/selectedprotocol).

The optional argument `shared` specifies whether additional
`RawSecureServerSocket` objects can bind to the same combination of
`address`, `port` and `v6Only`. If `shared` is `true` and more
`RawSecureServerSocket`s from this isolate or other isolates are bound
to the port, then the incoming connections will be distributed among all
the bound `RawSecureServerSocket`s. Connections can be distributed over
multiple isolates this way.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<RawSecureServerSocket> bind(
    address, int port, SecurityContext? context,
    {int backlog = 0,
    bool v6Only = false,
    bool requestClientCertificate = false,
    bool requireClientCertificate = false,
    List<String>? supportedProtocols,
    bool shared = false}) {
  return RawServerSocket.bind(address, port,
          backlog: backlog, v6Only: v6Only, shared: shared)
      .then((serverSocket) => new RawSecureServerSocket._(
          serverSocket,
          context,
          requestClientCertificate,
          requireClientCertificate,
          supportedProtocols));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSecureServerSocket/bind.html>
:::
