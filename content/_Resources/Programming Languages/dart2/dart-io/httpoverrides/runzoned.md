[dart:io](../../dart-io/dart-io-library){._links-link}

runZoned\<R\> method
====================

::: {.section .multi-line-signature}
R runZoned\<R\>(

1.  R body( ),
2.  {[HttpClient](../httpclient-class) createHttpClient(
    1.  [SecurityContext](../securitycontext-class)?

    )?,
3.  [String](../../dart-core/string-class) findProxyFromEnvironment(
    1.  [Uri](../../dart-core/uri-class) uri,
    2.  [Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
        [String](../../dart-core/string-class)\>? environment

    )?}

)
:::

Runs `body` in a fresh [Zone](../../dart-async/zone-class) using the
provided overrides.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static R runZoned<R>(R Function() body,
    {HttpClient Function(SecurityContext?)? createHttpClient,
    String Function(Uri uri, Map<String, String>? environment)?
        findProxyFromEnvironment}) {
  HttpOverrides overrides =
      _HttpOverridesScope(createHttpClient, findProxyFromEnvironment);
  return _asyncRunZoned<R>(body,
      zoneValues: {_httpOverridesToken: overrides});
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpOverrides/runZoned.html>
:::
