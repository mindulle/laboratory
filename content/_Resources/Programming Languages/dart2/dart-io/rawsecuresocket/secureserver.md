[dart:io](../../dart-io/dart-io-library){._links-link}

secureServer method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RawSecureSocket](../rawsecuresocket-class)\>
secureServer(

1.  [RawSocket](../rawsocket-class) socket,
2.  [SecurityContext](../securitycontext-class)? context,
3.  {[StreamSubscription](../../dart-async/streamsubscription-class)\<[RawSocketEvent](../rawsocketevent-class)\>?
    subscription,
4.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>?
    bufferedData,
5.  [bool](../../dart-core/bool-class) requestClientCertificate = false,
6.  [bool](../../dart-core/bool-class) requireClientCertificate = false,
7.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>?
    supportedProtocols}

)
:::

Initiates TLS on an existing server connection.

Takes an already connected `socket` and starts server side TLS handshake
to make the communication secure. When the returned future completes the
`RawSecureSocket` has completed the TLS handshake. Using this function
requires that the other end of the connection is going to start the TLS
handshake.

If the `socket` already has a subscription, pass the existing
subscription in the `subscription` parameter. The
[secureServer](secureserver) operation will take over the subscription
by replacing the handlers with it own secure processing. The caller must
not touch this subscription anymore. Passing a paused subscription is an
error.

If some of the data of the TLS handshake has already been read from the
socket this data can be passed in the `bufferedData` parameter. This
data will be processed before any other data available on the socket.

See [RawSecureServerSocket.bind](../rawsecureserversocket/bind) for more
information on the arguments.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<RawSecureSocket> secureServer(
    RawSocket socket, SecurityContext? context,
    {StreamSubscription<RawSocketEvent>? subscription,
    List<int>? bufferedData,
    bool requestClientCertificate = false,
    bool requireClientCertificate = false,
    List<String>? supportedProtocols}) {
  socket.readEventsEnabled = false;
  socket.writeEventsEnabled = false;
  return _RawSecureSocket.connect(
      socket.address, socket.remotePort, true, socket,
      context: context,
      subscription: subscription,
      bufferedData: bufferedData,
      requestClientCertificate: requestClientCertificate,
      requireClientCertificate: requireClientCertificate,
      supportedProtocols: supportedProtocols);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSecureSocket/secureServer.html>
:::
