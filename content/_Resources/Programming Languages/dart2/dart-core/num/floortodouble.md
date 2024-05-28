[dart:core](../../dart-core/dart-core-library){._links-link}

floorToDouble method
====================

::: {.section .multi-line-signature}
[double](../double-class) floorToDouble()
:::

Returns the greatest double integer value no greater than `this`.

If this is already an integer valued double, including `-0.0`, or it is
a non-finite double value, the value is returned unmodified.

For the purpose of rounding, `-0.0` is considered to be below `0.0`. A
number `d` in the range `0.0 < d < 1.0` will return `0.0`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double floorToDouble();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/floorToDouble.html>
:::
