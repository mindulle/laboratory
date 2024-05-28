[dart:html](../../dart-html/dart-html-library){._links-link}

result property
===============

::: {#getter .section .multi-line-signature}
[Object](../../dart-core/object-class)? result
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Object? get result {
  var res = JS('Null|String|NativeByteBuffer', '#.result', this);
  if (res is ByteBuffer) {
    return new Uint8List.view(res);
  }
  return res;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FileReader/result.html>
:::
