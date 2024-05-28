[dart:async](../../dart-async/dart-async-library){._links-link}

any method
==========

::: {.section .multi-line-signature}
[Future](../future-class)\<[bool](../../dart-core/bool-class)\> any(

1.  [bool](../../dart-core/bool-class) test(
    1.  T element

    )

)
:::

Checks whether `test` accepts any element provided by this stream.

Calls `test` on each element of this stream. If the call returns `true`,
the returned future is completed with `true` and processing stops.

If this stream ends without finding an element that `test` accepts, the
returned future is completed with `false`.

If this stream emits an error, or if the call to `test` throws, the
returned future is completed with that error, and processing stops.

Example:

``` {.language-dart data-language="dart"}
final result =
    await Stream.periodic(const Duration(seconds: 1), (count) => count)
        .take(15)
        .any((element) => element >= 5);

print(result); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<bool> any(bool test(T element)) {
  _Future<bool> future = new _Future<bool>();
  StreamSubscription<T> subscription =
      this.listen(null, onError: future._completeError, onDone: () {
    future._complete(false);
  }, cancelOnError: true);
  subscription.onData((T element) {
    _runUserCode(() => test(element), (bool isMatch) {
      if (isMatch) {
        _cancelAndValue(subscription, future, true);
      }
    }, _cancelAndErrorClosure(subscription, future));
  });
  return future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/any.html>
:::
