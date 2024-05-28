[dart:async](../../dart-async/dart-async-library){._links-link}

drain\<E\> method
=================

::: {.section .multi-line-signature}
[Future](../future-class)\<E\> drain\<E\>(

1.  \[E? futureValue\]

)
:::

Discards all data on this stream, but signals when it is done or an
error occurred.

When subscribing using [drain](drain), cancelOnError will be true. This
means that the future will complete with the first error on this stream
and then cancel the subscription.

If this stream emits an error, the returned future is completed with
that error, and processing is stopped.

In case of a `done` event the future completes with the given
`futureValue`.

The `futureValue` must not be omitted if `null` is not assignable to
`E`.

Example:

``` {.language-dart data-language="dart"}
final result = await Stream.fromIterable([1, 2, 3]).drain(100);
print(result); // Outputs: 100.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<E> drain<E>([E? futureValue]) {
  if (futureValue == null) {
    futureValue = futureValue as E;
  }
  return listen(null, cancelOnError: true).asFuture<E>(futureValue);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/drain.html>
:::
