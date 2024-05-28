[dart:io](../../dart-io/dart-io-library){._links-link}

authenticate property
=====================

::: {#setter .section .multi-line-signature}
void
authenticate=([Future](../../dart-async/future-class)\<[bool](../../dart-core/bool-class)\>
f([Uri](../../dart-core/uri-class) url,
[String](../../dart-core/string-class) scheme,
[String](../../dart-core/string-class)? realm)?)
:::

Sets the function to be called when a site is requesting authentication.

The URL requested, the authentication scheme and the security realm from
the server are passed in the arguments `f.url`, `f.scheme` and
`f.realm`.

The function returns a [Future](../../dart-async/future-class) which
should complete when the authentication has been resolved. If
credentials cannot be provided the
[Future](../../dart-async/future-class) should complete with `false`. If
credentials are available the function should add these using
[addCredentials](addcredentials) before completing the
[Future](../../dart-async/future-class) with the value `true`.

If the [Future](../../dart-async/future-class) completes with `true` the
request will be retried using the updated credentials, however, the
retried request will not carry the original request payload. Otherwise
response processing will continue normally.

If it is known that the remote server requires authentication for all
requests, it is advisable to use [addCredentials](addcredentials)
directly, or manually set the `'authorization'` header on the request to
avoid the overhead of a failed request, or issues due to missing request
payload on retried request.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void set authenticate(
    Future<bool> Function(Uri url, String scheme, String? realm)? f);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClient/authenticate.html>
:::
