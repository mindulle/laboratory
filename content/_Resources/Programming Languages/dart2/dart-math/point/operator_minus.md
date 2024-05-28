[dart:math](../../dart-math/dart-math-library){._links-link}

operator - method
=================

::: {.section .multi-line-signature}
[Point](../point-class)\<T\> operator -(

1.  [Point](../point-class)\<T\> other

)
:::

Subtract `other` from `this`, as if both points were vectors.

Returns the resulting \"vector\" as a Point.

Example:

``` {.language-dart data-language="dart"}
var point = const Point(10, 100) - const Point(10, 10); // Point(0, 90)
point = const Point(-10, -20) - const Point(10, 100); // Point(-110, -120)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Point<T> operator -(Point<T> other) {
  return Point<T>((x - other.x) as T, (y - other.y) as T);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Point/operator_minus.html>
:::
