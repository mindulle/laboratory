[dart:io](../../dart-io/dart-io-library){._links-link}

findProxyFromEnvironment method
===============================

::: {.section .multi-line-signature}
[String](../../dart-core/string-class) findProxyFromEnvironment(

1.  [Uri](../../dart-core/uri-class) url,
2.  [Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
    [String](../../dart-core/string-class)\>? environment

)
:::

Resolves the proxy server to be used for HTTP connections.

When this override is installed, this function overrides the behavior of
`HttpClient.findProxyFromEnvironment`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
String findProxyFromEnvironment(Uri url, Map<String, String>? environment) {
  return _HttpClient._findProxyFromEnvironment(url, environment);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpOverrides/findProxyFromEnvironment.html>
:::
