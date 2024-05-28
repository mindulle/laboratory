[dart:math](../../dart-math/dart-math-library){._links-link}

squaredDistanceTo method
========================

::: {.section .multi-line-signature}
T squaredDistanceTo(

1.  [Point](../point-class)\<T\> other

)
:::

Returns the squared distance between `this` and `other`.

Squared distances can be used for comparisons when the actual value is
not required.

Example:

``` {.language-dart data-language="dart"}
var squaredDistance =
    const Point(0, 0).squaredDistanceTo(const Point(0, 0)); // 0.0
squaredDistance =
    const Point(0, 0).squaredDistanceTo(const Point(10, 0)); // 100
squaredDistance =
    const Point(0, 0).squaredDistanceTo(const Point(0, -10)); // 100
squaredDistance =
    const Point(-10, 0).squaredDistanceTo(const Point(100, 0)); // 12100
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
T squaredDistanceTo(Point<T> other) {
  var dx = x - other.x;
  var dy = y - other.y;
  return (dx * dx + dy * dy) as T;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Point/squaredDistanceTo.html>
:::
