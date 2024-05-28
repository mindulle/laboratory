[dart:io](../../dart-io/dart-io-library){._links-link}

secureServer method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[SecureSocket](../securesocket-class)\>
secureServer(

1.  [Socket](../socket-class) socket,
2.  [SecurityContext](../securitycontext-class)? context,
3.  {[List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>?
    bufferedData,
4.  [bool](../../dart-core/bool-class) requestClientCertificate = false,
5.  [bool](../../dart-core/bool-class) requireClientCertificate = false,
6.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>?
    supportedProtocols}

)
:::

Initiates TLS on an existing server connection.

Takes an already connected `socket` and starts server side TLS handshake
to make the communication secure. When the returned future completes the
`SecureSocket` has completed the TLS handshake. Using this function
requires that the other end of the connection is going to start the TLS
handshake.

If the `socket` already has a subscription, this subscription will no
longer receive and events. In most cases calling
[StreamSubscription.pause](../../dart-async/streamsubscription/pause) on
this subscription before starting TLS handshake is the right thing to
do.

If some of the data of the TLS handshake has already been read from the
socket this data can be passed in the `bufferedData` parameter. This
data will be processed before any other data available on the socket.

See [SecureServerSocket.bind](../secureserversocket/bind) for more
information on the arguments.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<SecureSocket> secureServer(
    Socket socket, SecurityContext? context,
    {List<int>? bufferedData,
    bool requestClientCertificate = false,
    bool requireClientCertificate = false,
    List<String>? supportedProtocols}) {
  return ((socket as dynamic /*_Socket*/)._detachRaw() as Future)
      .then<RawSecureSocket>((detachedRaw) {
    return RawSecureSocket.secureServer(detachedRaw[0] as RawSocket, context,
        subscription: detachedRaw[1] as StreamSubscription<RawSocketEvent>?,
        bufferedData: bufferedData,
        requestClientCertificate: requestClientCertificate,
        requireClientCertificate: requireClientCertificate,
        supportedProtocols: supportedProtocols);
  }).then<SecureSocket>((raw) => new SecureSocket._(raw));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecureSocket/secureServer.html>
:::
