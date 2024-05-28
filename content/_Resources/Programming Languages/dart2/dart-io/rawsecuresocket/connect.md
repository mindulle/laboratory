[dart:io](../../dart-io/dart-io-library){._links-link}

connect method
==============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[RawSecureSocket](../rawsecuresocket-class)\>
connect(

1.  dynamic host,
2.  [int](../../dart-core/int-class) port,
3.  {[SecurityContext](../securitycontext-class)? context,
4.  [bool](../../dart-core/bool-class) onBadCertificate(
    1.  [X509Certificate](../x509certificate-class) certificate

    )?,
5.  void keyLog(
    1.  [String](../../dart-core/string-class) line

    )?,
6.  [List](../../dart-core/list-class)\<[String](../../dart-core/string-class)\>?
    supportedProtocols,
7.  [Duration](../../dart-core/duration-class)? timeout}

)

::: {.features}
override
:::
:::

Constructs a new secure client socket and connect it to the given host
on the given port.

The returned [Future](../../dart-async/future-class) is completed with
the `RawSecureSocket` when it is connected and ready for subscription.

The certificate provided by the server is checked using the trusted
certificates set in the SecurityContext object If a certificate and key
are set on the client, using
[SecurityContext.useCertificateChain](../securitycontext/usecertificatechain)
and [SecurityContext.usePrivateKey](../securitycontext/useprivatekey),
and the server asks for a client certificate, then that client
certificate is sent to the server.

`onBadCertificate` is an optional handler for unverifiable certificates.
The handler receives the [X509Certificate](../x509certificate-class),
and can inspect it and decide (or let the user decide) whether to accept
the connection or not. The handler should return true to continue the
`RawSecureSocket` connection.

`onBadCertificate` is an optional handler for unverifiable certificates.
The handler receives the [X509Certificate](../x509certificate-class),
and can inspect it and decide (or let the user decide) whether to accept
the connection or not. The handler should return true to continue the
[SecureSocket](../securesocket-class) connection.

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
[RawSecureSocket.selectedProtocol](selectedprotocol).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<RawSecureSocket> connect(host, int port,
    {SecurityContext? context,
    bool onBadCertificate(X509Certificate certificate)?,
    void keyLog(String line)?,
    List<String>? supportedProtocols,
    Duration? timeout}) {
  _RawSecureSocket._verifyFields(host, port, false, false);
  return RawSocket.connect(host, port, timeout: timeout).then((socket) {
    return secure(socket,
        context: context,
        onBadCertificate: onBadCertificate,
        keyLog: keyLog,
        supportedProtocols: supportedProtocols);
  });
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSecureSocket/connect.html>
:::
