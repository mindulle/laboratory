[dart:async](../../dart-async/dart-async-library){._links-link}

last property
=============

::: {#getter .section .multi-line-signature}
[Future](../future-class)\<T\> last
:::

The last element of this stream.

If this stream emits an error event, the returned future is completed
with that error and processing stops.

If this stream is empty (the done event is the first event), the
returned future completes with an error.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> get last {
  _Future<T> future = new _Future<T>();
  late T result;
  bool foundResult = false;
  listen(
      (T value) {
        foundResult = true;
        result = value;
      },
      onError: future._completeError,
      onDone: () {
        if (foundResult) {
          future._complete(result);
          return;
        }
        try {
          throw IterableElementError.noElement();
        } catch (e, s) {
          _completeWithErrorCallback(future, e, s);
        }
      },
      cancelOnError: true);
  return future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/last.html>
:::
