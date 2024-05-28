[dart:async](../../dart-async/dart-async-library){._links-link}

Stream\<T\>.multi constructor
=============================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.9\")

</div>

Stream\<T\>.multi(

1.  void onListen(
    1.  [MultiStreamController](../multistreamcontroller-class)\<T\>

    ),
2.  {[bool](../../dart-core/bool-class) isBroadcast = false}

)
:::

Creates a multi-subscription stream.

Each time the created stream is listened to, the `onListen` callback is
invoked with a new
[MultiStreamController](../multistreamcontroller-class), which forwards
events to the [StreamSubscription](../streamsubscription-class) returned
by that [listen](listen) call.

This allows each listener to be treated as an individual stream.

The [MultiStreamController](../multistreamcontroller-class) does not
support reading its
[StreamController.stream](../streamcontroller/stream). Setting its
[StreamController.onListen](../streamcontroller/onlisten) has no effect
since the `onListen` callback is called instead, and the
[StreamController.onListen](../streamcontroller/onlisten) won\'t be
called later. The controller acts like an asynchronous controller, but
provides extra methods for delivering events synchronously.

If `isBroadcast` is set to `true`, the returned stream\'s
[Stream.isBroadcast](isbroadcast) will be `true`. This has no effect on
the stream behavior, it is up to the `onListen` function to act like a
broadcast stream if it claims to be one.

A multi-subscription stream can behave like any other stream. If the
`onListen` callback throws on every call after the first, the stream
behaves like a single-subscription stream. If the stream emits the same
events to all current listeners, it behaves like a broadcast stream.

It can also choose to emit different events to different listeners. For
example, a stream which repeats the most recent non-`null` event to new
listeners, could be implemented as this example:

``` {.language-dart data-language="dart"}
extension StreamRepeatLatestExtension<T extends Object> on Stream<T> {
  Stream<T> repeatLatest() {
    var done = false;
    T? latest = null;
    var currentListeners = <MultiStreamController<T>>{};
    this.listen((event) {
      latest = event;
      for (var listener in [...currentListeners]) listener.addSync(event);
    }, onError: (Object error, StackTrace stack) {
      for (var listener in [...currentListeners]) listener.addErrorSync(error, stack);
    }, onDone: () {
      done = true;
      latest = null;
      for (var listener in currentListeners) listener.closeSync();
      currentListeners.clear();
    });
    return Stream.multi((controller) {
      if (done) {
        controller.close();
        return;
      }
      currentListeners.add(controller);
      var latestValue = latest;
      if (latestValue != null) controller.add(latestValue);
      controller.onCancel = () {
        currentListeners.remove(controller);
      };
    });
  }
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.9")
factory Stream.multi(void Function(MultiStreamController<T>) onListen,
    {bool isBroadcast = false}) {
  return _MultiStream<T>(onListen, isBroadcast);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/Stream.multi.html>
:::
