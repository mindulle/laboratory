[dart:core](../../dart-core/dart-core-library){._links-link}

operator \* method
==================

::: {.section .multi-line-signature}
[Duration](../duration-class) operator \*(

1.  [num](../num-class) factor

)
:::

Multiplies this Duration by the given `factor` and returns the result as
a new Duration object.

Note that when `factor` is a double, and the duration is greater than 53
bits, precision is lost because of double-precision arithmetic.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Duration operator *(num factor) {
  return Duration._microseconds((_duration * factor).round());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/operator_multiply.html>
:::
