[dart:core](../../dart-core/dart-core-library){._links-link}

elapsed property
================

::: {#getter .section .multi-line-signature}
[Duration](../duration-class) elapsed
:::

The [elapsedTicks](elapsedticks) counter converted to a
[Duration](../duration-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Duration get elapsed {
  return Duration(microseconds: elapsedMicroseconds);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Stopwatch/elapsed.html>
:::
