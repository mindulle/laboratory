[dart:async](../../dart-async/dart-async-library){._links-link}

asBroadcastStream method
========================

::: {.section .multi-line-signature}
[Stream](../stream-class)\<T\> asBroadcastStream(

1.  {void onListen(
    1.  [StreamSubscription](../streamsubscription-class)\<T\>
        subscription

    )?,
2.  void onCancel(
    1.  [StreamSubscription](../streamsubscription-class)\<T\>
        subscription

    )?}

)

::: {.features}
override
:::
:::

Returns a multi-subscription stream that produces the same events as
this.

The returned stream will subscribe to this stream when its first
subscriber is added, and will stay subscribed until this stream ends, or
a callback cancels the subscription.

If `onListen` is provided, it is called with a subscription-like object
that represents the underlying subscription to this stream. It is
possible to pause, resume or cancel the subscription during the call to
`onListen`. It is not possible to change the event handlers, including
using [StreamSubscription.asFuture](../streamsubscription/asfuture).

If `onCancel` is provided, it is called in a similar way to `onListen`
when the returned stream stops having listeners. If it later gets a new
listener, the `onListen` function is called again.

Use the callbacks, for example, for pausing the underlying subscription
while having no subscribers to prevent losing events, or canceling the
subscription when there are no listeners.

Cancelling is intended to be used when there are no current subscribers.
If the subscription passed to `onListen` or `onCancel` is cancelled,
then no further events are ever emitted by current subscriptions on the
returned broadcast stream, not even a done event.

Example:

``` {.language-dart data-language="dart"}
final stream =
    Stream<int>.periodic(const Duration(seconds: 1), (count) => count)
        .take(10);

final broadcastStream = stream.asBroadcastStream(
  onCancel: (controller) {
    print('Stream paused');
    controller.pause();
  },
  onListen: (controller) async {
    if (controller.isPaused) {
      print('Stream resumed');
      controller.resume();
    }
  },
);

final oddNumberStream = broadcastStream.where((event) => event.isOdd);
final oddNumberListener = oddNumberStream.listen(
      (event) {
    print('Odd: $event');
  },
  onDone: () => print('Done'),
);

final evenNumberStream = broadcastStream.where((event) => event.isEven);
final evenNumberListener = evenNumberStream.listen((event) {
  print('Even: $event');
}, onDone: () => print('Done'));

await Future.delayed(const Duration(milliseconds: 3500)); // 3.5 second
// Outputs:
// Even: 0
// Odd: 1
// Even: 2
oddNumberListener.cancel(); // Nothing printed.
evenNumberListener.cancel(); // "Stream paused"
await Future.delayed(const Duration(seconds: 2));
print(await broadcastStream.first); // "Stream resumed"
// Outputs:
// 3
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<T> asBroadcastStream(
        {void onListen(StreamSubscription<T> subscription)?,
        void onCancel(StreamSubscription<T> subscription)?}) =>
    _stream.asBroadcastStream(onListen: onListen, onCancel: onCancel);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamView/asBroadcastStream.html>
:::
