[dart:async](../../dart-async/dart-async-library){._links-link}

timeout method
==============

::: {.section .multi-line-signature}
[Stream](../stream-class)\<T\> timeout(

1.  [Duration](../../dart-core/duration-class) timeLimit,
2.  {void onTimeout(
    1.  [EventSink](../eventsink-class)\<T\> sink

    )?}

)
:::

Creates a new stream with the same events as this stream.

When someone is listening on the returned stream and more than
`timeLimit` passes without any event being emitted by this stream, the
`onTimeout` function is called, which can then emit further events on
the returned stream.

The countdown starts when the returned stream is listened to, and is
restarted when an event from this stream is emitted, or when listening
on the returned stream is paused and resumed. The countdown is stopped
when listening on the returned stream is paused or cancelled. No new
countdown is started when a countdown completes and the `onTimeout`
function is called, even if events are emitted. If the delay between
events of this stream is multiple times `timeLimit`, at most one timeout
will happen between events.

The `onTimeout` function is called with one argument: an
[EventSink](../eventsink-class) that allows putting events into the
returned stream. This `EventSink` is only valid during the call to
`onTimeout`. Calling [EventSink.close](../eventsink/close) on the sink
passed to `onTimeout` closes the returned stream, and no further events
are processed.

If `onTimeout` is omitted, a timeout will emit a
[TimeoutException](../timeoutexception-class) into the error channel of
the returned stream. If the call to `onTimeout` throws, the error is
emitted as an error on the returned stream.

The returned stream is a broadcast stream if this stream is. If a
broadcast stream is listened to more than once, each subscription will
have its individually timer that starts counting on listen, and the
subscriptions\' timers can be paused individually.

Example:

``` {.language-dart data-language="dart"}
Future<String> waitTask() async {
  return await Future.delayed(
      const Duration(seconds: 4), () => 'Complete');
}
final stream = Stream<String>.fromFuture(waitTask())
    .timeout(const Duration(seconds: 2), onTimeout: (controller) {
  print('TimeOut occurred');
  controller.close();
});

stream.listen(print, onDone: () => print('Done'));

// Outputs:
// TimeOut occurred
// Done
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<T> timeout(Duration timeLimit, {void onTimeout(EventSink<T> sink)?}) {
  _StreamControllerBase<T> controller;
  if (isBroadcast) {
    controller = new _SyncBroadcastStreamController<T>(null, null);
  } else {
    controller = new _SyncStreamController<T>(null, null, null, null);
  }

  Zone zone = Zone.current;
  // Register callback immediately.
  _TimerCallback timeoutCallback;
  if (onTimeout == null) {
    timeoutCallback = () {
      controller.addError(
          new TimeoutException("No stream event", timeLimit), null);
    };
  } else {
    var registeredOnTimeout =
        zone.registerUnaryCallback<void, EventSink<T>>(onTimeout);
    var wrapper = new _ControllerEventSinkWrapper<T>(null);
    timeoutCallback = () {
      wrapper._sink = controller; // Only valid during call.
      zone.runUnaryGuarded(registeredOnTimeout, wrapper);
      wrapper._sink = null;
    };
  }

  // All further setup happens inside `onListen`.
  controller.onListen = () {
    Timer timer = zone.createTimer(timeLimit, timeoutCallback);
    var subscription = this.listen(null);
    // Set up event forwarding. Each data or error event resets the timer
    subscription
      ..onData((T event) {
        timer.cancel();
        timer = zone.createTimer(timeLimit, timeoutCallback);
        // Controller is synchronous, and the call might close the stream
        // and cancel the timer,
        // so create the Timer before calling into add();
        // issue: https://github.com/dart-lang/sdk/issues/37565
        controller.add(event);
      })
      ..onError((Object error, StackTrace stackTrace) {
        timer.cancel();
        timer = zone.createTimer(timeLimit, timeoutCallback);
        controller._addError(
            error, stackTrace); // Avoid Zone error replacement.
      })
      ..onDone(() {
        timer.cancel();
        controller.close();
      });
    // Set up further controller callbacks.
    controller.onCancel = () {
      timer.cancel();
      return subscription.cancel();
    };
    if (!isBroadcast) {
      controller
        ..onPause = () {
          timer.cancel();
          subscription.pause();
        }
        ..onResume = () {
          subscription.resume();
          timer = zone.createTimer(timeLimit, timeoutCallback);
        };
    }
  };

  return controller.stream;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/timeout.html>
:::
