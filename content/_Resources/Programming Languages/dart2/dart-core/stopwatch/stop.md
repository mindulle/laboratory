[dart:core](../../dart-core/dart-core-library){._links-link}

stop method
===========

::: {.section .multi-line-signature}
void stop()
:::

Stops the [Stopwatch](../stopwatch-class).

The [elapsedTicks](elapsedticks) count stops increasing after this call.
If the [Stopwatch](../stopwatch-class) is currently not running, then
calling this method has no effect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void stop() {
  _stop ??= _now();
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Stopwatch/stop.html>
:::
