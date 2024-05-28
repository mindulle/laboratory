[dart:async](../../dart-async/dart-async-library){._links-link}

StreamTransformer\<S, T\> constructor
=====================================

::: {.section .multi-line-signature}
const StreamTransformer\<S, T\>(

1.  [StreamSubscription](../streamsubscription-class)\<T\> onListen(
    1.  [Stream](../stream-class)\<S\> stream,
    2.  [bool](../../dart-core/bool-class) cancelOnError

    )

)
:::

Creates a [StreamTransformer](../streamtransformer-class) based on the
given `onListen` callback.

The returned stream transformer uses the provided `onListen` callback
when a transformed stream is listened to. At that time, the callback
receives the input stream (the one passed to [bind](bind)) and a boolean
flag `cancelOnError` to create a
[StreamSubscription](../streamsubscription-class).

If the transformed stream is a broadcast stream, so is the stream
returned by the [StreamTransformer.bind](bind) method by this
transformer.

If the transformed stream is listened to multiple times, the `onListen`
callback is called again for each new [Stream.listen](../stream/listen)
call. This happens whether the stream is a broadcast stream or not, but
the call will usually fail for non-broadcast streams.

The `onListen` callback does *not* receive the handlers that were passed
to [Stream.listen](../stream/listen). These are automatically set after
the call to the `onListen` callback (using
[StreamSubscription.onData](../streamsubscription/ondata),
[StreamSubscription.onError](../streamsubscription/onerror) and
[StreamSubscription.onDone](../streamsubscription/ondone)).

Most commonly, an `onListen` callback will first call
[Stream.listen](../stream/listen) on the provided stream (with the
corresponding `cancelOnError` flag), and then return a new
[StreamSubscription](../streamsubscription-class).

There are two common ways to create a StreamSubscription:

1.  by allocating a [StreamController](../streamcontroller-class) and to
    return the result of listening to its stream. It\'s important to
    forward pause, resume and cancel events (unless the transformer
    intentionally wants to change this behavior).
2.  by creating a new class that implements
    [StreamSubscription](../streamsubscription-class). Note that the
    subscription should run callbacks in the [Zone](../zone-class) the
    stream was listened to (see [Zone](../zone-class) and
    [Zone.bindCallback](../zone/bindcallback)).

Example:

``` {.language-dart data-language="dart"}
/// Starts listening to [input] and duplicates all non-error events.
StreamSubscription<int> _onListen(Stream<int> input, bool cancelOnError) {
  // Create the result controller.
  // Using `sync` is correct here, since only async events are forwarded.
  var controller = StreamController<int>(sync: true);
  controller.onListen = () {
    var subscription = input.listen((data) {
      // Duplicate the data.
      controller.add(data);
      controller.add(data);
    },
        onError: controller.addError,
        onDone: controller.close,
        cancelOnError: cancelOnError);
    // Controller forwards pause, resume and cancel events.
    controller
      ..onPause = subscription.pause
      ..onResume = subscription.resume
      ..onCancel = subscription.cancel;
  };
  // Return a new [StreamSubscription] by listening to the controller's
  // stream.
  return controller.stream.listen(null);
}

// Instantiate a transformer:
var duplicator = const StreamTransformer<int, int>(_onListen);

// Use as follows:
intStream.transform(duplicator);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const factory StreamTransformer(
        StreamSubscription<T> onListen(
            Stream<S> stream, bool cancelOnError)) =
    _StreamSubscriptionTransformer<S, T>;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamTransformer/StreamTransformer.html>
:::
