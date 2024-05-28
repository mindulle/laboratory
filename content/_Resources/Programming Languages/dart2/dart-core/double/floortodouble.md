[dart:core](../../dart-core/dart-core-library){._links-link}

floorToDouble method
====================

::: {.section .multi-line-signature}
[double](../double-class) floorToDouble()

::: {.features}
override
:::
:::

Returns the greatest integer double value no greater than `this`.

If this is already an integer valued double, including `-0.0`, or it is
not a finite value, the value is returned unmodified.

For the purpose of rounding, `-0.0` is considered to be below `0.0`. A
number `d` in the range `0.0 < d < 1.0` will return `0.0`.

``` {.language-dart data-language="dart"}
print(1.99999.floorToDouble()); // 1.0
print(2.0.floorToDouble()); // 2.0
print(2.99999.floorToDouble()); // 2.0
print((-1.99999).floorToDouble()); // -2.0
print((-2.0).floorToDouble()); // -2.0
print((-2.00001).floorToDouble()); // -3.0
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double floorToDouble();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/floorToDouble.html>
:::
