[dart:core](../../dart-core/dart-core-library){._links-link}

roundToDouble method
====================

::: {.section .multi-line-signature}
[double](../double-class) roundToDouble()
:::

The double integer value closest to this value.

Rounds away from zero when there is no closest integer:
`(3.5).roundToDouble() == 4` and `(-3.5).roundToDouble() == -4`.

If this is already an integer valued double, including `-0.0`, or it is
a non-finite double value, the value is returned unmodified.

For the purpose of rounding, `-0.0` is considered to be below `0.0`, and
`-0.0` is therefore considered closer to negative numbers than `0.0`.
This means that for a value `d` in the range `-0.5 < d < 0.0`, the
result is `-0.0`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double roundToDouble();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/roundToDouble.html>
:::
