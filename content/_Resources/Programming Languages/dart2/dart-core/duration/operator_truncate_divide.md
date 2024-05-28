[dart:core](../../dart-core/dart-core-library){._links-link}

operator \~/ method
===================

::: {.section .multi-line-signature}
[Duration](../duration-class) operator \~/(

1.  [int](../int-class) quotient

)
:::

Divides this Duration by the given `quotient` and returns the truncated
result as a new Duration object.

Throws an
[IntegerDivisionByZeroException](../integerdivisionbyzeroexception-class){.deprecated}
if `quotient` is `0`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Duration operator ~/(int quotient) {
  // By doing the check here instead of relying on "~/" below we get the
  // exception even with dart2js.
  if (quotient == 0) throw IntegerDivisionByZeroException();
  return Duration._microseconds(_duration ~/ quotient);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/operator_truncate_divide.html>
:::
