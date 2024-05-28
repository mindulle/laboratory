[dart:io](../../dart-io/dart-io-library){._links-link}

startConnect method
===================

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[ConnectionTask](../connectiontask-class)\<[RawSecureSocket](../rawsecuresocket-class)\>\>
startConnect(

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
    supportedProtocols}

)

::: {.features}
override
:::
:::

Like [connect](connect), but returns a
[Future](../../dart-async/future-class) that completes with a
`ConnectionTask` that can be cancelled if the
[RawSecureSocket](../rawsecuresocket-class) is no longer needed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<ConnectionTask<RawSecureSocket>> startConnect(host, int port,
    {SecurityContext? context,
    bool onBadCertificate(X509Certificate certificate)?,
    void keyLog(String line)?,
    List<String>? supportedProtocols}) {
  return RawSocket.startConnect(host, port)
      .then((ConnectionTask<RawSocket> rawState) {
    Future<RawSecureSocket> socket = rawState.socket.then((rawSocket) {
      return secure(rawSocket,
          context: context,
          onBadCertificate: onBadCertificate,
          keyLog: keyLog,
          supportedProtocols: supportedProtocols);
    });
    return new ConnectionTask<RawSecureSocket>._(socket, rawState._onCancel);
  });
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/RawSecureSocket/startConnect.html>
:::
