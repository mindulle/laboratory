[dart:developer](../../dart-developer/dart-developer-library){._links-link}

serverWebSocketUri property
===========================

::: {#getter .section .multi-line-signature}
[Uri](../../dart-core/uri-class)? serverWebSocketUri
:::

The Uri to connect to the service via web socket. If the web server is
not running, this will be null.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uri? get serverWebSocketUri {
  Uri? uri = serverUri;
  if (uri != null) {
    final pathSegments = <String>[];
    if (uri.pathSegments.isNotEmpty) {
      pathSegments.addAll(uri.pathSegments.where(
        // Strip out the empty string that appears at the end of path segments.
        // Empty string elements will result in an extra '/' being added to the
        // URI.
        (s) => s.isNotEmpty,
      ));
    }
    pathSegments.add('ws');
    uri = uri.replace(scheme: 'ws', pathSegments: pathSegments);
  }
  return uri;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/ServiceProtocolInfo/serverWebSocketUri.html>
:::
