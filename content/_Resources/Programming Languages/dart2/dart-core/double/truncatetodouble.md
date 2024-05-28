[dart:core](../../dart-core/dart-core-library){._links-link}

truncateToDouble method
=======================

::: {.section .multi-line-signature}
[double](../double-class) truncateToDouble()

::: {.features}
override
:::
:::

Returns the integer double value obtained by discarding any fractional
digits from `this`.

If this is already an integer valued double, including `-0.0`, or it is
not a finite value, the value is returned unmodified.

For the purpose of rounding, `-0.0` is considered to be below `0.0`. A
number `d` in the range `-1.0 < d < 0.0` will return `-0.0`, and in the
range `0.0 < d < 1.0` it will return 0.0.

``` {.language-dart data-language="dart"}
print(2.5.truncateToDouble()); // 2.0
print(2.00001.truncateToDouble()); // 2.0
print(1.99999.truncateToDouble()); // 1.0
print(0.5.truncateToDouble()); // 0.0
print((-0.5).truncateToDouble()); // -0.0
print((-1.5).truncateToDouble()); // -1.0
print((-2.5).truncateToDouble()); // -2.0
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double truncateToDouble();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/double/truncateToDouble.html>
:::
