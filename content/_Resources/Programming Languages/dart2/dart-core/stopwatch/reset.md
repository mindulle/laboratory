[dart:core](../../dart-core/dart-core-library){._links-link}

reset method
============

::: {.section .multi-line-signature}
void reset()
:::

Resets the [elapsed](elapsed) count to zero.

This method does not stop or start the [Stopwatch](../stopwatch-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void reset() {
  _start = _stop ?? _now();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Stopwatch/reset.html>
:::
