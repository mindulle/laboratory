[dart:async](../../dart-async/dart-async-library){._links-link}

reduce method
=============

::: {.section .multi-line-signature}
[Future](../future-class)\<T\> reduce(

1.  T combine(
    1.  T previous,
    2.  T element

    )

)
:::

Combines a sequence of values by repeatedly applying `combine`.

Similar to [Iterable.reduce](../../dart-core/iterable/reduce), this
function maintains a value, starting with the first element of this
stream and updated for each further element of this stream. For each
element after the first, the value is updated to the result of calling
`combine` with the previous value and the element.

When this stream is done, the returned future is completed with the
value at that time.

If this stream is empty, the returned future is completed with an error.
If this stream emits an error, or the call to `combine` throws, the
returned future is completed with that error, and processing is stopped.

Example:

``` {.language-dart data-language="dart"}
final result = await Stream.fromIterable([2, 6, 10, 8, 2])
    .reduce((previous, element) => previous + element);
print(result); // 28
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> reduce(T combine(T previous, T element)) {
  _Future<T> result = new _Future<T>();
  bool seenFirst = false;
  late T value;
  StreamSubscription<T> subscription =
      this.listen(null, onError: result._completeError, onDone: () {
    if (!seenFirst) {
      try {
        // Throw and recatch, instead of just doing
        //  _completeWithErrorCallback, e, theError, StackTrace.current),
        // to ensure that the stackTrace is set on the error.
        throw IterableElementError.noElement();
      } catch (e, s) {
        _completeWithErrorCallback(result, e, s);
      }
    } else {
      result._complete(value);
    }
  }, cancelOnError: true);
  subscription.onData((T element) {
    if (seenFirst) {
      _runUserCode(() => combine(value, element), (T newValue) {
        value = newValue;
      }, _cancelAndErrorClosure(subscription, result));
    } else {
      value = element;
      seenFirst = true;
    }
  });
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/reduce.html>
:::
