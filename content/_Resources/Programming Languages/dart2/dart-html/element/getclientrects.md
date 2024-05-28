[dart:html](../../dart-html/dart-html-library){._links-link}

getClientRects method
=====================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>\>
getClientRects()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<Rectangle> getClientRects() {
  var value = _getClientRects();

  // If no prototype we need one for the world to hookup to the proper Dart class.
  var jsProto = JS('', '#.prototype', value);
  if (jsProto == null) {
    JS('', '#.prototype = Object.create(null)', value);
  }

  applyExtension('DOMRectList', value);

  return value;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/getClientRects.html>
:::
