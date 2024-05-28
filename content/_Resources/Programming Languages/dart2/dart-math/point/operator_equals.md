[dart:math](../../dart-math/dart-math-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) operator ==(

1.  [Object](../../dart-core/object-class) other

)

::: {.features}
override
:::
:::

Whether `other` is a point with the same coordinates as this point.

Returns `true` if `other` is a [Point](../point-class) with [x](x) and
[y](y) coordinates equal to the corresponding coordinates of this point,
and `false` otherwise.

Example:

``` {.language-dart data-language="dart"}
var result = const Point(0, 0) == const Point(0, 0); // true
result = const Point(1.0, 0) == const Point(-1.0, 0); // false
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator ==(Object other) =>
    other is Point && x == other.x && y == other.y;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Point/operator_equals.html>
:::
