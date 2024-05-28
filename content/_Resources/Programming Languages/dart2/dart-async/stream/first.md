[dart:async](../../dart-async/dart-async-library){._links-link}

first property
==============

::: {#getter .section .multi-line-signature}
[Future](../future-class)\<T\> first
:::

The first element of this stream.

Stops listening to this stream after the first element has been
received.

Internally the method cancels its subscription after the first element.
This means that single-subscription (non-broadcast) streams are closed
and cannot be reused after a call to this getter.

If an error event occurs before the first data event, the returned
future is completed with that error.

If this stream is empty (a done event occurs before the first data
event), the returned future completes with an error.

Except for the type of the error, this method is equivalent to
`this.elementAt(0)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> get first {
  _Future<T> future = new _Future<T>();
  StreamSubscription<T> subscription =
      this.listen(null, onError: future._completeError, onDone: () {
    try {
      throw IterableElementError.noElement();
    } catch (e, s) {
      _completeWithErrorCallback(future, e, s);
    }
  }, cancelOnError: true);
  subscription.onData((T value) {
    _cancelAndValue(subscription, future, value);
  });
  return future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/first.html>
:::
