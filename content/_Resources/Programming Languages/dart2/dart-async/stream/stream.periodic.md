[dart:async](../../dart-async/dart-async-library){._links-link}

Stream\<T\>.periodic constructor
================================

::: {.section .multi-line-signature}
Stream\<T\>.periodic(

1.  [Duration](../../dart-core/duration-class) period,
2.  \[T computation(
    1.  [int](../../dart-core/int-class) computationCount

    )?\]

)
:::

Creates a stream that repeatedly emits events at `period` intervals.

The event values are computed by invoking `computation`. The argument to
this callback is an integer that starts with 0 and is incremented for
every event.

The `period` must be a non-negative
[Duration](../../dart-core/duration-class).

If `computation` is omitted, the event values will all be `null`.

The `computation` must not be omitted if the event type `T` does not
allow `null` as a value.

Example:

``` {.language-dart data-language="dart"}
final stream =
    Stream<int>.periodic(const Duration(
        seconds: 1), (count) => count * count).take(5);

stream.forEach(print); // Outputs event values 0,1,4,9,16.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Stream.periodic(Duration period,
    [T computation(int computationCount)?]) {
  if (computation == null && !typeAcceptsNull<T>()) {
    throw ArgumentError.value(null, "computation",
        "Must not be omitted when the event type is non-nullable");
  }
  var controller = _SyncStreamController<T>(null, null, null, null);
  // Counts the time that the Stream was running (and not paused).
  Stopwatch watch = new Stopwatch();
  controller.onListen = () {
    int computationCount = 0;
    void sendEvent(_) {
      watch.reset();
      if (computation != null) {
        T event;
        try {
          event = computation(computationCount++);
        } catch (e, s) {
          controller.addError(e, s);
          return;
        }
        controller.add(event);
      } else {
        controller.add(null as T); // We have checked that null is T.
      }
    }

    Timer timer = Timer.periodic(period, sendEvent);
    controller
      ..onCancel = () {
        timer.cancel();
        return Future._nullFuture;
      }
      ..onPause = () {
        watch.stop();
        timer.cancel();
      }
      ..onResume = () {
        Duration elapsed = watch.elapsed;
        watch.start();
        timer = new Timer(period - elapsed, () {
          timer = Timer.periodic(period, sendEvent);
          sendEvent(null);
        });
      };
  };
  return controller.stream;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/Stream.periodic.html>
:::
