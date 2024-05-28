[dart:async](../../dart-async/dart-async-library){._links-link}

Timer constructor
=================

::: {.section .multi-line-signature}
Timer(

1.  [Duration](../../dart-core/duration-class) duration,
2.  void callback( )

)
:::

Creates a new timer.

The `callback` function is invoked after the given `duration`.

Example:

``` {.language-dart data-language="dart"}
final timer =
    Timer(const Duration(seconds: 5), () => print('Timer finished'));
// Outputs after 5 seconds: "Timer finished".
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Timer(Duration duration, void Function() callback) {
  if (Zone.current == Zone.root) {
    // No need to bind the callback. We know that the root's timer will
    // be invoked in the root zone.
    return Zone.current.createTimer(duration, callback);
  }
  return Zone.current
      .createTimer(duration, Zone.current.bindCallbackGuarded(callback));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Timer/Timer.html>
:::
