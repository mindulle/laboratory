[dart:async](../../dart-async/dart-async-library){._links-link}

Stream\<T\>.fromFutures constructor
===================================

::: {.section .multi-line-signature}
Stream\<T\>.fromFutures(

1.  [Iterable](../../dart-core/iterable-class)\<[Future](../future-class)\<T\>\>
    futures

)
:::

Create a single-subscription stream from a group of futures.

The stream reports the results of the futures on the stream in the order
in which the futures complete. Each future provides either a data event
or an error event, depending on how the future completes.

If some futures have already completed when `Stream.fromFutures` is
called, their results will be emitted in some unspecified order.

When all futures have completed, the stream is closed.

If `futures` is empty, the stream closes as soon as possible.

Example:

``` {.language-dart data-language="dart"}
Future<int> waitTask() async {
  await Future.delayed(const Duration(seconds: 2));
  return 10;
}

Future<String> doneTask() async {
  await Future.delayed(const Duration(seconds: 5));
  return 'Future complete';
}

final stream = Stream<Object>.fromFutures([doneTask(), waitTask()]);
stream.listen(print, onDone: () => print('Done'), onError: print);

// Outputs:
// 10 after 'waitTask' finished.
// "Future complete" after 'doneTask' finished.
// "Done" when stream completed.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Stream.fromFutures(Iterable<Future<T>> futures) {
  _StreamController<T> controller =
      new _SyncStreamController<T>(null, null, null, null);
  int count = 0;
  // Declare these as variables holding closures instead of as
  // function declarations.
  // This avoids creating a new closure from the functions for each future.
  void onValue(T value) {
    if (!controller.isClosed) {
      controller._add(value);
      if (--count == 0) controller._closeUnchecked();
    }
  }

  void onError(Object error, StackTrace stack) {
    if (!controller.isClosed) {
      controller._addError(error, stack);
      if (--count == 0) controller._closeUnchecked();
    }
  }

  // The futures are already running, so start listening to them immediately
  // (instead of waiting for the stream to be listened on).
  // If we wait, we might not catch errors in the futures in time.
  for (var future in futures) {
    count++;
    future.then(onValue, onError: onError);
  }
  // Use schedule microtask since controller is sync.
  if (count == 0) scheduleMicrotask(controller.close);
  return controller.stream;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/Stream.fromFutures.html>
:::
