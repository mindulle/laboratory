[dart:async](../../dart-async/dart-async-library){._links-link}

Stream\<T\>.fromFuture constructor
==================================

::: {.section .multi-line-signature}
Stream\<T\>.fromFuture(

1.  [Future](../future-class)\<T\> future

)
:::

Creates a new single-subscription stream from the future.

When the future completes, the stream will fire one event, either data
or error, and then close with a done-event.

Example:

``` {.language-dart data-language="dart"}
Future<String> futureTask() async {
  await Future.delayed(const Duration(seconds: 5));
  return 'Future complete';
}

final stream = Stream<String>.fromFuture(futureTask());
stream.listen(print,
    onDone: () => print('Done'), onError: print);

// Outputs:
// "Future complete" after 'futureTask' finished.
// "Done" when stream completed.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Stream.fromFuture(Future<T> future) {
  // Use the controller's buffering to fill in the value even before
  // the stream has a listener. For a single value, it's not worth it
  // to wait for a listener before doing the `then` on the future.
  _StreamController<T> controller =
      new _SyncStreamController<T>(null, null, null, null);
  future.then((value) {
    controller._add(value);
    controller._closeUnchecked();
  }, onError: (error, stackTrace) {
    controller._addError(error, stackTrace);
    controller._closeUnchecked();
  });
  return controller.stream;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/Stream.fromFuture.html>
:::
