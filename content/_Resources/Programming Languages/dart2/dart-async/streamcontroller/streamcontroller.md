[dart:async](../../dart-async/dart-async-library){._links-link}

StreamController\<T\> constructor
=================================

::: {.section .multi-line-signature}
StreamController\<T\>(

1.  {void onListen( )?,
2.  void onPause( )?,
3.  void onResume( )?,
4.  [FutureOr](../futureor-class)\<void\> onCancel( )?,
5.  [bool](../../dart-core/bool-class) sync = false}

)
:::

A controller with a [stream](stream) that supports only one single
subscriber.

If `sync` is true, the returned stream controller is a
[SynchronousStreamController](../synchronousstreamcontroller-class), and
must be used with the care and attention necessary to not break the
[Stream](../stream-class) contract. If in doubt, use the non-sync
version.

Using an asynchronous controller will never give the wrong behavior, but
using a synchronous controller incorrectly can cause otherwise correct
programs to break.

A synchronous controller is only intended for optimizing event
propagation when one asynchronous event immediately triggers another. It
should not be used unless the calls to [add](add) or
[addError](adderror) are guaranteed to occur in places where it won\'t
break `Stream` invariants.

Use synchronous controllers only to forward (potentially transformed)
events from another stream or a future.

A Stream should be inert until a subscriber starts listening on it
(using the `onListen` callback to start producing events). Streams
should not leak resources (like websockets) when no user ever listens on
the stream.

The controller buffers all incoming events until a subscriber is
registered, but this feature should only be used in rare circumstances.

The `onPause` function is called when the stream becomes paused.
`onResume` is called when the stream resumed.

The `onListen` callback is called when the stream receives its listener
and `onCancel` when the listener ends its subscription. If `onCancel`
needs to perform an asynchronous operation, `onCancel` should return a
future that completes when the cancel operation is done.

If the stream is canceled before the controller needs data the
`onResume` call might not be executed.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory StreamController(
    {void onListen()?,
    void onPause()?,
    void onResume()?,
    FutureOr<void> onCancel()?,
    bool sync = false}) {
  return sync
      ? _SyncStreamController<T>(onListen, onPause, onResume, onCancel)
      : _AsyncStreamController<T>(onListen, onPause, onResume, onCancel);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/StreamController.html>
:::
