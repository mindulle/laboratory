[dart:async](../../dart-async/dart-async-library){._links-link}

length property
===============

::: {#getter .section .multi-line-signature}
[Future](../future-class)\<[int](../../dart-core/int-class)\> length
:::

The number of elements in this stream.

Waits for all elements of this stream. When this stream ends, the
returned future is completed with the number of elements.

If this stream emits an error, the returned future is completed with
that error, and processing stops.

This operation listens to this stream, and a non-broadcast stream cannot
be reused after finding its length.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<int> get length {
  _Future<int> future = new _Future<int>();
  int count = 0;
  this.listen(
      (_) {
        count++;
      },
      onError: future._completeError,
      onDone: () {
        future._complete(count);
      },
      cancelOnError: true);
  return future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/length.html>
:::
