[dart:async](../../dart-async/dart-async-library){._links-link}

singleWhere method
==================

::: {.section .multi-line-signature}
[Future](../future-class)\<T\> singleWhere(

1.  [bool](../../dart-core/bool-class) test(
    1.  T element

    ),
2.  {T orElse( )?}

)
:::

Finds the single element in this stream matching `test`.

Like [lastWhere](lastwhere), except that it is an error if more than one
matching element occurs in this stream.

Example:

``` {.language-dart data-language="dart"}
var result = await Stream.fromIterable([1, 2, 3, 6, 9, 12])
    .singleWhere((element) => element % 4 == 0, orElse: () => -1);
print(result); // 12

result = await Stream.fromIterable([2, 6, 8, 12, 24, 32])
    .singleWhere((element) => element % 9 == 0, orElse: () => -1);
print(result); // -1

result = await Stream.fromIterable([2, 6, 8, 12, 24, 32])
    .singleWhere((element) => element % 6 == 0, orElse: () => -1);
// Throws.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> singleWhere(bool test(T element), {T orElse()?}) {
  _Future<T> future = new _Future<T>();
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
        if (foundResult) {
          try {
            throw IterableElementError.tooMany();
          } catch (e, s) {
            _cancelAndErrorWithReplacement(subscription, future, e, s);
          }
          return;
        }
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
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/singleWhere.html>
:::
