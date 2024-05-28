[dart:math](../dart-math/dart-math-library){._links-link}

atan2 function
==============

::: {.section .multi-line-signature}
[double](../dart-core/double-class) atan2(

1.  [num](../dart-core/num-class) a,
2.  [num](../dart-core/num-class) b

)
:::

A variant of [atan](atan).

Converts both arguments to [double](../dart-core/double-class)s.

Returns the angle in radians between the positive x-axis and the vector
(`b`,`a`). The result is in the range -PI..PI.

If `b` is positive, this is the same as `atan(a/b)`.

The result is negative when `a` is negative (including when `a` is the
double -0.0).

If `a` is equal to zero, the vector (`b`,`a`) is considered parallel to
the x-axis, even if `b` is also equal to zero. The sign of `b`
determines the direction of the vector along the x-axis.

Returns NaN if either argument is NaN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external double atan2(num a, num b);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/atan2.html>
:::
