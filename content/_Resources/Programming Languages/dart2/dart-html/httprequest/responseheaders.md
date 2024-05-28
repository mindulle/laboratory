[dart:html](../../dart-html/dart-html-library){._links-link}

responseHeaders property
========================

::: {#getter .section .multi-line-signature}
[Map](../../dart-core/map-class)\<[String](../../dart-core/string-class),
[String](../../dart-core/string-class)\> responseHeaders
:::

Returns all response headers as a key-value map.

Multiple values for the same header key can be combined into one,
separated by a comma and a space.

See:
<http://www.w3.org/TR/XMLHttpRequest/#the-getresponseheader()-method>

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Map<String, String> get responseHeaders {
  // from Closure's goog.net.Xhrio.getResponseHeaders.
  var headers = <String, String>{};
  var headersString = this.getAllResponseHeaders();
  if (headersString == null) {
    return headers;
  }
  var headersList = headersString.split('\r\n');
  for (var header in headersList) {
    if (header.isEmpty) {
      continue;
    }

    var splitIdx = header.indexOf(': ');
    if (splitIdx == -1) {
      continue;
    }
    var key = header.substring(0, splitIdx).toLowerCase();
    var value = header.substring(splitIdx + 2);
    if (headers.containsKey(key)) {
      headers[key] = '${headers[key]}, $value';
    } else {
      headers[key] = value;
    }
  }
  return headers;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/HttpRequest/responseHeaders.html>
:::
