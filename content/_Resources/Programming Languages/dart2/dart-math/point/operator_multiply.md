[dart:math](../../dart-math/dart-math-library){._links-link}

operator \* method
==================

::: {.section .multi-line-signature}
[Point](../point-class)\<T\> operator \*(

1.  [num](../../dart-core/num-class) factor

)
:::

Scale this point by `factor` as if it were a vector.

**Important Note**: This function accepts a `num` as its argument only
so that you can scale `Point<double>` objects by an `int` factor.
Because the `*` operator always returns the same type of `Point` as it
is called on, passing in a double `factor` on a `Point<int>` *causes*
*a* *runtime* *error*.

Example:

``` {.language-dart data-language="dart"}
// Integer values.
var point = const Point(10, 100) * 10; // Point(100, 1000)
point = const Point(-10, -100) * 5; // Point(-50, -500)
// Double values.
var doublePoint = Point(10.0, 100.0) * 1.5; // Point(15.0, 150.0)
// Runtime error due the invalid type cast.
var newPoint = const Point(10, 100) * 1.5; // Throws.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Point<T> operator *(num /*T|int*/ factor) {
  return Point<T>((x * factor) as T, (y * factor) as T);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Point/operator_multiply.html>
:::
