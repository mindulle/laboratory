[dart:async](../../dart-async/dart-async-library){._links-link}

take method
===========

::: {.section .multi-line-signature}
[Stream](../stream-class)\<T\> take(

1.  [int](../../dart-core/int-class) count

)
:::

Provides at most the first `count` data events of this stream.

Returns a stream that emits the same events that this stream would if
listened to at the same time, until either this stream ends or it has
emitted `count` data events, at which point the returned stream is done.

If this stream produces fewer than `count` data events before it\'s
done, so will the returned stream.

Starts listening to this stream when the returned stream is listened to
and stops listening when the first `count` data events have been
received.

This means that if this is a single-subscription (non-broadcast) streams
it cannot be reused after the returned stream has been listened to.

If this is a broadcast stream, the returned stream is a broadcast
stream. In that case, the events are only counted from the time the
returned stream is listened to.

Example:

``` {.language-dart data-language="dart"}
final stream =
    Stream<int>.periodic(const Duration(seconds: 1), (i) => i)
        .take(60);
stream.forEach(print); // Outputs events: 0, ... 59.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<T> take(int count) {
  return new _TakeStream<T>(this, count);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/take.html>
:::
