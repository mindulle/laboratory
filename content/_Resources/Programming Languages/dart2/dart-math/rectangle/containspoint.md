[dart:math](../../dart-math/dart-math-library){._links-link}

containsPoint method
====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) containsPoint(

1.  [Point](../point-class)\<[num](../../dart-core/num-class)\> another

)

::: {.features}
inherited
:::
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
<https://api.dart.dev/stable/2.18.5/dart-math/Rectangle/containsPoint.html>
:::
