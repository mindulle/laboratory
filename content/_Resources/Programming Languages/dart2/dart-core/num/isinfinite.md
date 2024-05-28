[dart:core](../../dart-core/dart-core-library){._links-link}

isInfinite property
===================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isInfinite
:::

Whether this number is positive infinity or negative infinity.

Only satisfied by [double.infinity](../double/infinity-constant) and
[double.negativeInfinity](../double/negativeinfinity-constant).

All numbers satisfy exactly one of `isInfinite`, [isFinite](isfinite)
and [isNaN](isnan).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isInfinite;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/isInfinite.html>
:::
