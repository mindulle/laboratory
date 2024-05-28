[dart:core](../../dart-core/dart-core-library){._links-link}

isNaN property
==============

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isNaN
:::

Whether this number is a Not-a-Number value.

Is `true` if this number is the [double.nan](../double/nan-constant)
value or any other of the possible [double](../double-class) NaN values.
Is `false` if this number is an integer, a finite double or an infinite
double ([double.infinity](../double/infinity-constant) or
[double.negativeInfinity](../double/negativeinfinity-constant)).

All numbers satisfy exactly one of [isInfinite](isinfinite),
[isFinite](isfinite) and `isNaN`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isNaN;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/isNaN.html>
:::
