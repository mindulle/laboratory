[dart:async](../../dart-async/dart-async-library){._links-link}

single property
===============

::: {#getter .section .multi-line-signature}
[Future](../future-class)\<T\> single
:::

The single element of this stream.

If this stream emits an error event, the returned future is completed
with that error and processing stops.

If [this](../stream-class) is empty or has more than one element, the
returned future completes with an error.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> get single {
  _Future<T> future = new _Future<T>();
  late T result;
  bool foundResult = false;
  StreamSubscription<T> subscription =
      this.listen(null, onError: future._completeError, onDone: () {
    if (foundResult) {
      future._complete(result);
      return;
    }
    try {
      throw IterableElementError.noElement();
    } catch (e, s) {
      _completeWithErrorCallback(future, e, s);
    }
  }, cancelOnError: true);
  subscription.onData((T value) {
    if (foundResult) {
      // This is the second element we get.
      try {
        throw IterableElementError.tooMany();
      } catch (e, s) {
        _cancelAndErrorWithReplacement(subscription, future, e, s);
      }
      return;
    }
    foundResult = true;
    result = value;
  });
  return future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/single.html>
:::
