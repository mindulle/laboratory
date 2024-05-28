[dart:core](../../dart-core/dart-core-library){._links-link}

current property
================

::: {#getter .section .multi-line-signature}
[int](../int-class) current

::: {.features}
override
:::
:::

The rune (integer Unicode code point) starting at the current position
in the string.

The value is -1 if there is no current code point.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get current => _currentCodePoint;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RuneIterator/current.html>
:::
