[dart:async](../../dart-async/dart-async-library){._links-link}

skipWhile method
================

::: {.section .multi-line-signature}
[Stream](../stream-class)\<T\> skipWhile(

1.  [bool](../../dart-core/bool-class) test(
    1.  T element

    )

)
:::

Skip data events from this stream while they are matched by `test`.

Returns a stream that emits the same events as this stream, except that
data events are not emitted until a data event fails `test`. The test
fails when called with a data event if it returns a non-`true` value or
if the call to `test` throws. If the call throws, the error is emitted
as an error event on the returned stream instead of the data event,
otherwise the event that made `test` return non-true is emitted as the
first data event.

Error and done events are provided by the returned stream unmodified.

The returned stream is a broadcast stream if this stream is. For a
broadcast stream, the events are only tested from the time the returned
stream is listened to.

Example:

``` {.language-dart data-language="dart"}
final stream = Stream<int>.periodic(const Duration(seconds: 1), (i) => i)
    .take(10)
    .skipWhile((x) => x < 5);
stream.forEach(print); // Outputs events: 5, ..., 9.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<T> skipWhile(bool test(T element)) {
  return new _SkipWhileStream<T>(this, test);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/skipWhile.html>
:::
