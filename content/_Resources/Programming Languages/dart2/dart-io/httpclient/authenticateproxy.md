[dart:io](../../dart-io/dart-io-library){._links-link}

authenticateProxy property
==========================

::: {#setter .section .multi-line-signature}
void
authenticateProxy=([Future](../../dart-async/future-class)\<[bool](../../dart-core/bool-class)\>
f([String](../../dart-core/string-class) host,
[int](../../dart-core/int-class) port,
[String](../../dart-core/string-class) scheme,
[String](../../dart-core/string-class)? realm)?)
:::

Sets the function to be called when a proxy is requesting
authentication.

Information on the proxy in use, the authentication scheme and the
security realm for the authentication are passed in the arguments
`f.host`, `f.port`, `f.scheme` and `f.realm`.

The function returns a [Future](../../dart-async/future-class) which
should complete when the authentication has been resolved. If
credentials cannot be provided the
[Future](../../dart-async/future-class) should complete with `false`. If
credentials are available the function should add these using
[addProxyCredentials](addproxycredentials) before completing the
[Future](../../dart-async/future-class) with the value `true`.

If the [Future](../../dart-async/future-class) completes with `true` the
request will be retried using the updated credentials. Otherwise
response processing will continue normally.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set authenticateProxy(
    Future<bool> Function(
            String host, int port, String scheme, String? realm)?
        f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/authenticateProxy.html>
:::
