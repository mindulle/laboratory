[dart:async](../../dart-async/dart-async-library){._links-link}

isEmpty property
================

::: {#getter .section .multi-line-signature}
[Future](../future-class)\<[bool](../../dart-core/bool-class)\> isEmpty
:::

Whether this stream contains any elements.

Waits for the first element of this stream, then completes the returned
future with `false`. If this stream ends without emitting any elements,
the returned future is completed with `true`.

If the first event is an error, the returned future is completed with
that error.

This operation listens to this stream, and a non-broadcast stream cannot
be reused after checking whether it is empty.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<bool> get isEmpty {
  _Future<bool> future = new _Future<bool>();
  StreamSubscription<T> subscription =
      this.listen(null, onError: future._completeError, onDone: () {
    future._complete(true);
  }, cancelOnError: true);
  subscription.onData((_) {
    _cancelAndValue(subscription, future, false);
  });
  return future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/isEmpty.html>
:::
