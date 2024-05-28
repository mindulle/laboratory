[dart:math](../../dart-math/dart-math-library){._links-link}

distanceTo method
=================

::: {.section .multi-line-signature}
[double](../../dart-core/double-class) distanceTo(

1.  [Point](../point-class)\<T\> other

)
:::

Returns the distance between `this` and `other`.

``` {.language-dart data-language="dart"}
var distanceTo = const Point(0, 0).distanceTo(const Point(0, 0)); // 0.0
distanceTo = const Point(0, 0).distanceTo(const Point(10, 0)); // 10.0
distanceTo = const Point(0, 0).distanceTo(const Point(0, -10)); // 10.0
distanceTo = const Point(-10, 0).distanceTo(const Point(100, 0)); // 110.0
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double distanceTo(Point<T> other) {
  var dx = x - other.x;
  var dy = y - other.y;
  return sqrt(dx * dx + dy * dy);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Point/distanceTo.html>
:::
