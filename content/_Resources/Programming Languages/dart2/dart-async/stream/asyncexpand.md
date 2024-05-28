[dart:async](../../dart-async/dart-async-library){._links-link}

asyncExpand\<E\> method
=======================

::: {.section .multi-line-signature}
[Stream](../stream-class)\<E\> asyncExpand\<E\>(

1.  [Stream](../stream-class)\<E\>? convert(
    1.  T event

    )

)
:::

Transforms each element into a sequence of asynchronous events.

Returns a new stream and for each event of this stream, do the
following:

-   If the event is an error event or a done event, it is emitted
    directly by the returned stream.
-   Otherwise it is an element. Then the `convert` function is called
    with the element as argument to produce a convert-stream for the
    element.
-   If that call throws, the error is emitted on the returned stream.
-   If the call returns `null`, no further action is taken for the
    elements.
-   Otherwise, this stream is paused and convert-stream is listened to.
    Every data and error event of the convert-stream is emitted on the
    returned stream in the order it is produced. When the convert-stream
    ends, this stream is resumed.

The returned stream is a broadcast stream if this stream is.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<E> asyncExpand<E>(Stream<E>? convert(T event)) {
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
    subscription.onData((T event) {
      Stream<E>? newStream;
      try {
        newStream = convert(event);
      } catch (e, s) {
        controller.addError(e, s);
        return;
      }
      if (newStream != null) {
        subscription.pause();
        controller.addStream(newStream).whenComplete(subscription.resume);
      }
    });
    controller.onCancel = subscription.cancel;
    if (!isBroadcast) {
      controller
        ..onPause = subscription.pause
        ..onResume = subscription.resume;
    }
  };
  return controller.stream;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/asyncExpand.html>
:::
