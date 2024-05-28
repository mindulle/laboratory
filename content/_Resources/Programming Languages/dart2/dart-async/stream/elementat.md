[dart:async](../../dart-async/dart-async-library){._links-link}

elementAt method
================

::: {.section .multi-line-signature}
[Future](../future-class)\<T\> elementAt(

1.  [int](../../dart-core/int-class) index

)
:::

Returns the value of the `index`th data event of this stream.

Stops listening to this stream after the `index`th data event has been
received.

Internally the method cancels its subscription after these elements.
This means that single-subscription (non-broadcast) streams are closed
and cannot be reused after a call to this method.

If an error event occurs before the value is found, the future completes
with this error.

If a done event occurs before the value is found, the future completes
with a [RangeError](../../dart-core/rangeerror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> elementAt(int index) {
  RangeError.checkNotNegative(index, "index");
  _Future<T> result = new _Future<T>();
  int elementIndex = 0;
  StreamSubscription<T> subscription;
  subscription =
      this.listen(null, onError: result._completeError, onDone: () {
    result._completeError(
        new RangeError.index(index, this, "index", null, elementIndex),
        StackTrace.empty);
  }, cancelOnError: true);
  subscription.onData((T value) {
    if (index == elementIndex) {
      _cancelAndValue(subscription, result, value);
      return;
    }
    elementIndex += 1;
  });

  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/elementAt.html>
:::
