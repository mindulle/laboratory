[dart:core](../../dart-core/dart-core-library){._links-link}

operator unary- method
======================

::: {.section .multi-line-signature}
[Duration](../duration-class) operator unary-()
:::

Creates a new [Duration](../duration-class) with the opposite direction
of this [Duration](../duration-class).

The returned [Duration](../duration-class) has the same length as this
one, but will have the opposite sign (as reported by
[isNegative](isnegative)) as this one where possible.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// Using subtraction helps dart2js avoid negative zeros.
Duration operator -() => Duration._microseconds(0 - _duration);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/operator_unary_minus.html>
:::
