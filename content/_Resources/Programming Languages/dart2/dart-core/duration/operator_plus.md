[dart:core](../../dart-core/dart-core-library){._links-link}

operator + method
=================

::: {.section .multi-line-signature}
[Duration](../duration-class) operator +(

1.  [Duration](../duration-class) other

)
:::

Adds this Duration and `other` and returns the sum as a new Duration
object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Duration operator +(Duration other) {
  return Duration._microseconds(_duration + other._duration);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/operator_plus.html>
:::
