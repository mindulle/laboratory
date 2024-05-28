[dart:async](../../dart-async/dart-async-library){._links-link}

asyncMap\<E\> method
====================

::: {.section .multi-line-signature}
[Stream](../stream-class)\<E\> asyncMap\<E\>(

1.  [FutureOr](../futureor-class)\<E\> convert(
    1.  T event

    )

)
:::

Creates a new stream with each data event of this stream asynchronously
mapped to a new event.

This acts like [map](map), except that `convert` may return a
[Future](../future-class), and in that case, this stream waits for that
future to complete before continuing with its result.

The returned stream is a broadcast stream if this stream is.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<E> asyncMap<E>(FutureOr<E> convert(T event)) {
  _StreamControllerBase<E> controller;
  if (isBroadcast) {
    controller = _SyncBroadcastStreamController<E>(null, null);
  } else {
    controller = _SyncStreamController<E>(null, null, null, null);
  }

  controller.onListen = () {
    StreamSubscription<T> subscription = this.listen(null,
        onError: controller._addError, // Avoid Zone error replacement.
        onDone: controller.close);
    FutureOr<Null> add(E value) {
      controller.add(value);
    }

    final addError = controller._addError;
    final resume = subscription.resume;
    subscription.onData((T event) {
      FutureOr<E> newValue;
      try {
        newValue = convert(event);
      } catch (e, s) {
        controller.addError(e, s);
        return;
      }
      if (newValue is Future<E>) {
        subscription.pause();
        newValue.then(add, onError: addError).whenComplete(resume);
      } else {
        // TODO(40014): Remove cast when type promotion works.
        controller.add(newValue as dynamic);
      }
    });
    controller.onCancel = subscription.cancel;
    if (!isBroadcast) {
      controller
        ..onPause = subscription.pause
        ..onResume = resume;
    }
  };
  return controller.stream;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/asyncMap.html>
:::
