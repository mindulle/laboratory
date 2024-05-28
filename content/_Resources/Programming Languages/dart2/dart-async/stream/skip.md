[dart:async](../../dart-async/dart-async-library){._links-link}

skip method
===========

::: {.section .multi-line-signature}
[Stream](../stream-class)\<T\> skip(

1.  [int](../../dart-core/int-class) count

)
:::

Skips the first `count` data events from this stream.

Returns a stream that emits the same events as this stream would if
listened to at the same time, except that the first `count` data events
are not emitted. The returned stream is done when this stream is.

If this stream emits fewer than `count` data events before being done,
the returned stream emits no data events.

The returned stream is a broadcast stream if this stream is. For a
broadcast stream, the events are only counted from the time the returned
stream is listened to.

Example:

``` {.language-dart data-language="dart"}
final stream =
    Stream<int>.periodic(const Duration(seconds: 1), (i) => i).skip(7);
stream.forEach(print); // Skips events 0, ..., 6. Outputs events: 7, ...
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<T> skip(int count) {
  return new _SkipStream<T>(this, count);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/skip.html>
:::
