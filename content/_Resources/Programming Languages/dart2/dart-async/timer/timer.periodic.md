[dart:async](../../dart-async/dart-async-library){._links-link}

Timer.periodic constructor
==========================

::: {.section .multi-line-signature}
Timer.periodic(

1.  [Duration](../../dart-core/duration-class) duration,
2.  void callback(
    1.  [Timer](../timer-class) timer

    )

)
:::

Creates a new repeating timer.

The `callback` is invoked repeatedly with `duration` intervals until
canceled with the [cancel](cancel) function.

The exact timing depends on the underlying timer implementation. No more
than `n` callbacks will be made in `duration * n` time, but the time
between two consecutive callbacks can be shorter and longer than
`duration`.

In particular, an implementation may schedule the next callback, e.g., a
`duration` after either when the previous callback ended, when the
previous callback started, or when the previous callback was scheduled
for - even if the actual callback was delayed.

`duration` must a non-negative
[Duration](../../dart-core/duration-class).

Example:

``` {.language-dart data-language="dart"}
var counter = 3;
Timer.periodic(const Duration(seconds: 2), (timer) {
  print(timer.tick);
  counter--;
  if (counter == 0) {
    print('Cancel timer');
    timer.cancel();
  }
});
// Outputs:
// 1
// 2
// 3
// "Cancel timer"
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Timer.periodic(Duration duration, void callback(Timer timer)) {
  if (Zone.current == Zone.root) {
    // No need to bind the callback. We know that the root's timer will
    // be invoked in the root zone.
    return Zone.current.createPeriodicTimer(duration, callback);
  }
  var boundCallback = Zone.current.bindUnaryCallbackGuarded<Timer>(callback);
  return Zone.current.createPeriodicTimer(duration, boundCallback);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Timer/Timer.periodic.html>
:::
