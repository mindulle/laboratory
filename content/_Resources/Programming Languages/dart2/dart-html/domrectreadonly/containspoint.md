[dart:html](../../dart-html/dart-html-library){._links-link}

containsPoint method
====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) containsPoint(

1.  [Point](../../dart-math/point-class)\<[num](../../dart-core/num-class)\>
    another

)
:::

Tests whether `another` is inside or along the edges of `this`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool containsPoint(Point<num> another) {
  return another.x >= left &&
      another.x <= left + width &&
      another.y >= top &&
      another.y <= top + height;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomRectReadOnly/containsPoint.html>
:::
