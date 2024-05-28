[dart:async](../../dart-async/dart-async-library){._links-link}

where method
============

::: {.section .multi-line-signature}
[Stream](../stream-class)\<T\> where(

1.  [bool](../../dart-core/bool-class) test(
    1.  T event

    )

)
:::

Creates a new stream from this stream that discards some elements.

The new stream sends the same error and done events as this stream, but
it only sends the data events that satisfy the `test`.

If the `test` function throws, the data event is dropped and the error
is emitted on the returned stream instead.

The returned stream is a broadcast stream if this stream is. If a
broadcast stream is listened to more than once, each subscription will
individually perform the `test`.

Example:

``` {.language-dart data-language="dart"}
final stream =
    Stream<int>.periodic(const Duration(seconds: 1), (count) => count)
        .take(10);

final customStream = stream.where((event) => event > 3 && event <= 6);
customStream.listen(print); // Outputs event values: 4,5,6.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<T> where(bool test(T event)) {
  return new _WhereStream<T>(this, test);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/where.html>
:::
