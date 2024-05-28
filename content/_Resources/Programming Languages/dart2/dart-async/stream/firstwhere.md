[dart:async](../../dart-async/dart-async-library){._links-link}

firstWhere method
=================

::: {.section .multi-line-signature}
[Future](../future-class)\<T\> firstWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  T element

    ),
2.  {T orElse( )?}

)
:::

Finds the first element of this stream matching `test`.

Returns a future that is completed with the first element of this stream
for which `test` returns `true`.

If no such element is found before this stream is done, and an `orElse`
function is provided, the result of calling `orElse` becomes the value
of the future. If `orElse` throws, the returned future is completed with
that error.

If this stream emits an error before the first matching element, the
returned future is completed with that error, and processing stops.

Stops listening to this stream after the first matching element or error
has been received.

Internally the method cancels its subscription after the first element
that matches the predicate. This means that single-subscription
(non-broadcast) streams are closed and cannot be reused after a call to
this method.

If an error occurs, or if this stream ends without finding a match and
with no `orElse` function provided, the returned future is completed
with an error.

Example:

``` {.language-dart data-language="dart"}
var result = await Stream.fromIterable([1, 3, 4, 9, 12])
    .firstWhere((element) => element % 6 == 0, orElse: () => -1);
print(result); // 12

result = await Stream.fromIterable([1, 2, 3, 4, 5])
    .firstWhere((element) => element % 6 == 0, orElse: () => -1);
print(result); // -1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> firstWhere(bool test(T element), {T orElse()?}) {
  _Future<T> future = new _Future();
  StreamSubscription<T> subscription =
      this.listen(null, onError: future._completeError, onDone: () {
    if (orElse != null) {
      _runUserCode(orElse, future._complete, future._completeError);
      return;
    }
    try {
      // Sets stackTrace on error.
      throw IterableElementError.noElement();
    } catch (e, s) {
      _completeWithErrorCallback(future, e, s);
    }
  }, cancelOnError: true);

  subscription.onData((T value) {
    _runUserCode(() => test(value), (bool isMatch) {
      if (isMatch) {
        _cancelAndValue(subscription, future, value);
      }
    }, _cancelAndErrorClosure(subscription, future));
  });
  return future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/firstWhere.html>
:::
