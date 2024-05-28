[dart:core](../../dart-core/dart-core-library){._links-link}

isNegative property
===================

::: {#getter .section .multi-line-signature}
[bool](../bool-class) isNegative
:::

Whether this [Duration](../duration-class) is negative.

A negative [Duration](../duration-class) represents the difference from
a later time to an earlier time.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool get isNegative => _duration < 0;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Duration/isNegative.html>
:::
