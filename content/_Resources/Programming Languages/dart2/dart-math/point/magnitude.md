[dart:math](../../dart-math/dart-math-library){._links-link}

magnitude property
==================

::: {#getter .section .multi-line-signature}
[double](../../dart-core/double-class) magnitude
:::

Get the straight line (Euclidean) distance between the origin (0, 0) and
this point.

Example:

``` {.language-dart data-language="dart"}
var magnitude = const Point(0, 0).magnitude; // 0.0
magnitude = const Point(10, 0).magnitude;  // 10.0
magnitude = const Point(0, -10).magnitude; // 10.0
magnitude = const Point(10, 10).magnitude;  // 14.142135623730951
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double get magnitude => sqrt(x * x + y * y);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Point/magnitude.html>
:::
