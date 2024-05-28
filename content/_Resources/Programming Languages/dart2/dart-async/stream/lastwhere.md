[dart:async](../../dart-async/dart-async-library){._links-link}

lastWhere method
================

::: {.section .multi-line-signature}
[Future](../future-class)\<T\> lastWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  T element

    ),
2.  {T orElse( )?}

)
:::

Finds the last element in this stream matching `test`.

If this stream emits an error, the returned future is completed with
that error, and processing stops.

Otherwise as [firstWhere](firstwhere), except that the last matching
element is found instead of the first. That means that a non-error
result cannot be provided before this stream is done.

Example:

``` {.language-dart data-language="dart"}
var result = await Stream.fromIterable([1, 3, 4, 7, 12, 24, 32])
    .lastWhere((element) => element % 6 == 0, orElse: () => -1);
print(result); // 24

result = await Stream.fromIterable([1, 3, 4, 7, 12, 24, 32])
    .lastWhere((element) => element % 10 == 0, orElse: () => -1);
print(result); // -1
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> lastWhere(bool test(T element), {T orElse()?}) {
  _Future<T> future = new _Future();
  late T result;
  bool foundResult = false;
  StreamSubscription<T> subscription =
      this.listen(null, onError: future._completeError, onDone: () {
    if (foundResult) {
      future._complete(result);
      return;
    }
    if (orElse != null) {
      _runUserCode(orElse, future._complete, future._completeError);
      return;
    }
    try {
      throw IterableElementError.noElement();
    } catch (e, s) {
      _completeWithErrorCallback(future, e, s);
    }
  }, cancelOnError: true);

  subscription.onData((T value) {
    _runUserCode(() => test(value), (bool isMatch) {
      if (isMatch) {
        foundResult = true;
        result = value;
      }
    }, _cancelAndErrorClosure(subscription, future));
  });
  return future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/lastWhere.html>
:::
