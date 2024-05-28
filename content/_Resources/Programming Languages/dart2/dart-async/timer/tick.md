[dart:async](../../dart-async/dart-async-library){._links-link}

tick property
=============

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) tick
:::

The number of durations preceding the most recent timer event.

The value starts at zero and is incremented each time a timer event
occurs, so each callback will see a larger value than the previous one.

If a periodic timer with a non-zero duration is delayed too much, so
more than one tick should have happened, all but the last tick in the
past are considered \"missed\", and no callback is invoked for them. The
[tick](tick) count reflects the number of durations that have passed and
not the number of callback invocations that have happened.

Example:

``` {.language-dart data-language="dart"}
final stopwatch = Stopwatch()..start();
Timer.periodic(const Duration(seconds: 1), (timer) {
  print(timer.tick);
  if (timer.tick == 1) {
    while (stopwatch.elapsedMilliseconds < 4500) {
      // Run uninterrupted for another 3.5 seconds!
      // The latest due tick after that is the 4-second tick.
    }
  } else {
    timer.cancel();
  }
});
// Outputs:
// 1
// 4
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get tick;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Timer/tick.html>
:::
