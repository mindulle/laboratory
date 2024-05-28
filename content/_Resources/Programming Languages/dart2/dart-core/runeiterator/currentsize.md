[dart:core](../../dart-core/dart-core-library){._links-link}

currentSize property
====================

::: {#getter .section .multi-line-signature}
[int](../int-class) currentSize
:::

The number of code units comprising the current rune.

Returns zero if there is no current rune ([current](current) is -1).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get currentSize => _nextPosition - _position;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RuneIterator/currentSize.html>
:::
