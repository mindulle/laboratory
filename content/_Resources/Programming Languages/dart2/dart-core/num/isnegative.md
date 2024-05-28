[dart:core](../../dart-core/dart-core-library){._links-link}

isNegative property
===================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isNegative
:::

Whether this number is negative.

A number is negative if it\'s smaller than zero, or if it is the double
`-0.0`. This precludes a NaN value like
[double.nan](../double/nan-constant) from being negative.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isNegative;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/num/isNegative.html>
:::
