[dart:async](../../dart-async/dart-async-library){._links-link}

expand\<S\> method
==================

::: {.section .multi-line-signature}
[Stream](../stream-class)\<S\> expand\<S\>(

1.  [Iterable](../../dart-core/iterable-class)\<S\> convert(
    1.  T element

    )

)
:::

Transforms each element of this stream into a sequence of elements.

Returns a new stream where each element of this stream is replaced by
zero or more data events. The event values are provided as an
[Iterable](../../dart-core/iterable-class) by a call to `convert` with
the element as argument, and the elements of that iterable is emitted in
iteration order. If calling `convert` throws, or if the iteration of the
returned values throws, the error is emitted on the returned stream and
iteration ends for that element of this stream.

Error events and the done event of this stream are forwarded directly to
the returned stream.

The returned stream is a broadcast stream if this stream is. If a
broadcast stream is listened to more than once, each subscription will
individually call `convert` and expand the events.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<S> expand<S>(Iterable<S> convert(T element)) {
  return new _ExpandStream<T, S>(this, convert);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/expand.html>
:::
