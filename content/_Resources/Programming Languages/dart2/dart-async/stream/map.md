[dart:async](../../dart-async/dart-async-library){._links-link}

map\<S\> method
===============

::: {.section .multi-line-signature}
[Stream](../stream-class)\<S\> map\<S\>(

1.  S convert(
    1.  T event

    )

)
:::

Transforms each element of this stream into a new stream event.

Creates a new stream that converts each element of this stream to a new
value using the `convert` function, and emits the result.

For each data event, `o`, in this stream, the returned stream provides a
data event with the value `convert(o)`. If `convert` throws, the
returned stream reports it as an error event instead.

Error and done events are passed through unchanged to the returned
stream.

The returned stream is a broadcast stream if this stream is. The
`convert` function is called once per data event per listener. If a
broadcast stream is listened to more than once, each subscription will
individually call `convert` on each data event.

Unlike [transform](transform), this method does not treat the stream as
chunks of a single value. Instead each event is converted independently
of the previous and following events, which may not always be correct.
For example, UTF-8 encoding, or decoding, will give wrong results if a
surrogate pair, or a multibyte UTF-8 encoding, is split into separate
events, and those events are attempted encoded or decoded independently.

Example:

``` {.language-dart data-language="dart"}
final stream =
    Stream<int>.periodic(const Duration(seconds: 1), (count) => count)
        .take(5);

final calculationStream =
    stream.map<String>((event) => 'Square: ${event * event}');
calculationStream.forEach(print);
// Square: 0
// Square: 1
// Square: 4
// Square: 9
// Square: 16
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<S> map<S>(S convert(T event)) {
  return new _MapStream<T, S>(this, convert);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/map.html>
:::
