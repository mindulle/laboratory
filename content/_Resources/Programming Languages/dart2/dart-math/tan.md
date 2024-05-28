[dart:math](../dart-math/dart-math-library){._links-link}

tan function
============

::: {.section .multi-line-signature}
[double](../dart-core/double-class) tan(

1.  [num](../dart-core/num-class) radians

)
:::

Converts `radians` to a [double](../dart-core/double-class) and returns
the tangent of the value.

The tangent function is equivalent to `sin(radians)/cos(radians)` and
may be infinite (positive or negative) when `cos(radians)` is equal to
zero. If `radians` is not a finite number, the result is NaN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external double tan(num radians);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/tan.html>
:::
