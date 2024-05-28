[dart:core](../../dart-core/dart-core-library){._links-link}

start method
============

::: {.section .multi-line-signature}
void start()
:::

Starts the [Stopwatch](../stopwatch-class).

The [elapsed](elapsed) count increases monotonically. If the
[Stopwatch](../stopwatch-class) has been stopped, then calling start
again restarts it without resetting the [elapsed](elapsed) count.

If the [Stopwatch](../stopwatch-class) is currently running, then
calling start does nothing.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void start() {
  int? stop = _stop;
  if (stop != null) {
    // (Re)start this stopwatch.
    // Don't count the time while the stopwatch has been stopped.
    _start += _now() - stop;
    _stop = null;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Stopwatch/start.html>
:::
