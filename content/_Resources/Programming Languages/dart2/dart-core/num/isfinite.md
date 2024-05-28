[dart:core](../../dart-core/dart-core-library){._links-link}

isFinite property
=================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isFinite
:::

Whether this number is finite.

The only non-finite numbers are NaN values, positive infinity, and
negative infinity. All integers are finite.

All numbers satisfy exactly one of [isInfinite](isinfinite), `isFinite`
and [isNaN](isnan).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isFinite;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/isFinite.html>
:::
