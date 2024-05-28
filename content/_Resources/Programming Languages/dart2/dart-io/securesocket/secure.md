[dart:io](../../dart-io/dart-io-library){._links-link}

secure method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[SecureSocket](../securesocket-class)\>
secure(

1.  [Socket](../socket-class) socket,
2.  {dynamic host,
3.  [SecurityContext](../securitycontext-class)? context,
4.  [bool](../../dart-core/bool-class) onBadCertificate(
    1.  [X509Certificate](../x509certificate-class) certificate

    )?,
5.  void keyLog(
    1.  [String](../../dart-core/string-class) line

    )?,
6.  \@Since(\"2.6\")
    [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>?
    supportedProtocols}

)
:::

Initiates TLS on an existing connection.

Takes an already connected `socket` and starts client side TLS handshake
to make the communication secure. When the returned future completes the
`SecureSocket` has completed the TLS handshake. Using this function
requires that the other end of the connection is prepared for TLS
handshake.

If the `socket` already has a subscription, this subscription will no
longer receive and events. In most cases calling
[StreamSubscription.pause](../../dart-async/streamsubscription/pause) on
this subscription before starting TLS handshake is the right thing to
do.

The given `socket` is closed and may not be used anymore.

If the `host` argument is passed it will be used as the host name for
the TLS handshake. If `host` is not passed the host name from the
`socket` will be used. The `host` can be either a
[String](../../dart-core/string-class) or an
[InternetAddress](../internetaddress-class).

`onBadCertificate` is an optional handler for unverifiable certificates.
The handler receives the [X509Certificate](../x509certificate-class),
and can inspect it and decide (or let the user decide) whether to accept
the connection or not. The handler should return true to continue the
`SecureSocket` connection.

`keyLog` is an optional callback that will be called when new TLS keys
are exchanged with the server. `keyLog` will receive one line of text in
[NSS Key Log
Format](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/NSS/Key_Log_Format)
for each call. Writing these lines to a file will allow tools (such as
[Wireshark](https://gitlab.com/wireshark/wireshark/-/wikis/TLS#tls-decryption))
to decrypt content sent through this socket. This is meant to allow
network-level debugging of secure sockets and should not be used in
production code. For example:

``` {.language-dart data-language="dart"}
final log = File('keylog.txt');
final socket = await SecureSocket.connect('www.example.com', 443,
    keyLog: (line) => log.writeAsStringSync(line, mode: FileMode.append));
```

`supportedProtocols` is an optional list of protocols (in decreasing
order of preference) to use during the ALPN protocol negotiation with
the server. Example values are \"http/1.1\" or \"h2\". The selected
protocol can be obtained via
[SecureSocket.selectedProtocol](selectedprotocol).

Calling this function will *not* cause a DNS host lookup. If the `host`
passed is a [String](../../dart-core/string-class), the
[InternetAddress](../internetaddress-class) for the resulting
`SecureSocket` will have the passed in `host` as its host value and the
internet address of the already connected socket as its address value.

See [connect](connect) for more information on the arguments.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<SecureSocket> secure(Socket socket,
    {host,
    SecurityContext? context,
    bool onBadCertificate(X509Certificate certificate)?,
    void keyLog(String line)?,
    @Since("2.6") List<String>? supportedProtocols}) {
  return ((socket as dynamic /*_Socket*/)._detachRaw() as Future)
      .then<RawSecureSocket>((detachedRaw) {
    return RawSecureSocket.secure(detachedRaw[0] as RawSocket,
        subscription: detachedRaw[1] as StreamSubscription<RawSocketEvent>?,
        host: host,
        context: context,
        onBadCertificate: onBadCertificate,
        keyLog: keyLog,
        supportedProtocols: supportedProtocols);
  }).then<SecureSocket>((raw) => new SecureSocket._(raw));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/SecureSocket/secure.html>
:::
