[dart:async](../../dart-async/dart-async-library){._links-link}

StreamController\<T\>.broadcast constructor
===========================================

::: {.section .multi-line-signature}
StreamController\<T\>.broadcast(

1.  {void onListen( )?,
2.  void onCancel( )?,
3.  [bool](../../dart-core/bool-class) sync = false}

)
:::

A controller where [stream](stream) can be listened to more than once.

The [Stream](../stream-class) returned by [stream](stream) is a
broadcast stream. It can be listened to more than once.

A Stream should be inert until a subscriber starts listening on it
(using the `onListen` callback to start producing events). Streams
should not leak resources (like websockets) when no user ever listens on
the stream.

Broadcast streams do not buffer events when there is no listener.

The controller distributes any events to all currently subscribed
listeners at the time when [add](add), [addError](adderror) or
[close](close) is called. It is not allowed to call `add`, `addError`,
or `close` before a previous call has returned. The controller does not
have any internal queue of events, and if there are no listeners at the
time the event is added, it will just be dropped, or, if it is an error,
be reported as uncaught.

Each listener subscription is handled independently, and if one pauses,
only the pausing listener is affected. A paused listener will buffer
events internally until unpaused or canceled.

If `sync` is true, events may be fired directly by the stream\'s
subscriptions during an [add](add), [addError](adderror) or
[close](close) call. The returned stream controller is a
[SynchronousStreamController](../synchronousstreamcontroller-class), and
must be used with the care and attention necessary to not break the
[Stream](../stream-class) contract. See
[Completer.sync](../completer/completer.sync) for some explanations on
when a synchronous dispatching can be used. If in doubt, keep the
controller non-sync.

If `sync` is false, the event will always be fired at a later time,
after the code adding the event has completed. In that case, no
guarantees are given with regard to when multiple listeners get the
events, except that each listener will get all events in the correct
order. Each subscription handles the events individually. If two events
are sent on an async controller with two listeners, one of the listeners
may get both events before the other listener gets any. A listener must
be subscribed both when the event is initiated (that is, when [add](add)
is called) and when the event is later delivered, in order to receive
the event.

The `onListen` callback is called when the first listener is subscribed,
and the `onCancel` is called when there are no longer any active
listeners. If a listener is added again later, after the `onCancel` was
called, the `onListen` will be called again.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory StreamController.broadcast(
    {void onListen()?, void onCancel()?, bool sync = false}) {
  return sync
      ? _SyncBroadcastStreamController<T>(onListen, onCancel)
      : _AsyncBroadcastStreamController<T>(onListen, onCancel);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamController/StreamController.broadcast.html>
:::
