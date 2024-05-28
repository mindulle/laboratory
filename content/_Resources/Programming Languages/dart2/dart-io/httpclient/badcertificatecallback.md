[dart:io](../../dart-io/dart-io-library){._links-link}

badCertificateCallback property
===============================

::: {#setter .section .multi-line-signature}
void badCertificateCallback=([bool](../../dart-core/bool-class)
callback([X509Certificate](../x509certificate-class) cert,
[String](../../dart-core/string-class) host,
[int](../../dart-core/int-class) port)?)
:::

Sets a callback that will decide whether to accept a secure connection
with a server certificate that cannot be authenticated by any of our
trusted root certificates.

When an secure HTTP request if made, using this HttpClient, and the
server returns a server certificate that cannot be authenticated, the
callback is called asynchronously with the
[X509Certificate](../x509certificate-class) object and the server\'s
hostname and port. If the value of
[badCertificateCallback](badcertificatecallback) is `null`, the bad
certificate is rejected, as if the callback returned `false`

If the callback returns true, the secure connection is accepted and the
`Future<HttpClientRequest>` that was returned from the call making the
request completes with a valid HttpRequest object. If the callback
returns false, the `Future<HttpClientRequest>` completes with an
exception.

If a bad certificate is received on a connection attempt, the library
calls the function that was the value of badCertificateCallback at the
time the request is made, even if the value of badCertificateCallback
has changed since then.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set badCertificateCallback(
    bool Function(X509Certificate cert, String host, int port)? callback);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/badCertificateCallback.html>
:::
