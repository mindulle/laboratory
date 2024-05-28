[dart:html](../../dart-html/dart-html-library){._links-link}

WebSocket constructor
=====================

::: {.section .multi-line-signature}
WebSocket(

1.  [String](../../dart-core/string-class) url,
2.  \[[Object](../../dart-core/object-class)? protocols\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory WebSocket(String url, [Object? protocols]) {
  if (protocols != null) {
    return WebSocket._create_1(url, protocols);
  }
  return WebSocket._create_2(url);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/WebSocket/WebSocket.html>
:::
