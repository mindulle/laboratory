[dart:html](../../dart-html/dart-html-library){._links-link}

toBlob method
=============

::: {.section .multi-line-signature}
[Future](../../dart-async/future-class)\<[Blob](../blob-class)\> toBlob(

1.  \[[String](../../dart-core/string-class)? type,
2.  [Object](../../dart-core/object-class)? arguments\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Blob> toBlob([String? type, Object? arguments]) {
  var completer = new Completer<Blob>();
  _toBlob((value) {
    completer.complete(value);
  }, type, arguments);
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasElement/toBlob.html>
:::
