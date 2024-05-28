[dart:async](../../dart-async/dart-async-library){._links-link}

fold\<S\> method
================

::: {.section .multi-line-signature}
[Future](../future-class)\<S\> fold\<S\>(

1.  S initialValue,
2.  S combine(
    1.  S previous,
    2.  T element

    )

)
:::

Combines a sequence of values by repeatedly applying `combine`.

Similar to [Iterable.fold](../../dart-core/iterable/fold), this function
maintains a value, starting with `initialValue` and updated for each
element of this stream. For each element, the value is updated to the
result of calling `combine` with the previous value and the element.

When this stream is done, the returned future is completed with the
value at that time. For an empty stream, the future is completed with
`initialValue`.

If this stream emits an error, or the call to `combine` throws, the
returned future is completed with that error, and processing is stopped.

Example:

``` {.language-dart data-language="dart"}
final result = await Stream.fromIterable([2, 6, 10, 8, 2])
    .fold<int>(10, (previous, element) => previous + element);
print(result); // 38
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<S> fold<S>(S initialValue, S combine(S previous, T element)) {
  _Future<S> result = new _Future<S>();
  S value = initialValue;
  StreamSubscription<T> subscription =
      this.listen(null, onError: result._completeError, onDone: () {
    result._complete(value);
  }, cancelOnError: true);
  subscription.onData((T element) {
    _runUserCode(() => combine(value, element), (S newValue) {
      value = newValue;
    }, _cancelAndErrorClosure(subscription, result));
  });
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/fold.html>
:::
