[dart:core](../../dart-core/dart-core-library){._links-link}

elapsedTicks property
=====================

::: {#getter .section .multi-line-signature}
[int](../int-class) elapsedTicks
:::

The elapsed number of clock ticks since calling [start](start) while the
[Stopwatch](../stopwatch-class) is running.

This is the elapsed number of clock ticks between calling [start](start)
and calling [stop](stop).

Is 0 if the [Stopwatch](../stopwatch-class) has never been started.

The elapsed number of clock ticks increases by [frequency](frequency)
every second.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get elapsedTicks {
  return (_stop ?? _now()) - _start;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Stopwatch/elapsedTicks.html>
:::
