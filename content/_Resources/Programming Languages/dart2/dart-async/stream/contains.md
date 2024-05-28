[dart:async](../../dart-async/dart-async-library){._links-link}

contains method
===============

::: {.section .multi-line-signature}
[Future](../future-class)\<[bool](../../dart-core/bool-class)\>
contains(

1.  [Object](../../dart-core/object-class)? needle

)
:::

Returns whether `needle` occurs in the elements provided by this stream.

Compares each element of this stream to `needle` using
[Object.==](../../dart-core/object/operator_equals). If an equal element
is found, the returned future is completed with `true`. If this stream
ends without finding a match, the future is completed with `false`.

If this stream emits an error, or the call to
[Object.==](../../dart-core/object/operator_equals) throws, the returned
future is completed with that error, and processing stops.

Example:

``` {.language-dart data-language="dart"}
final result = await Stream.fromIterable(['Year', 2021, 12, 24, 'Dart'])
    .contains('Dart');
print(result); // true
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<bool> contains(Object? needle) {
  _Future<bool> future = new _Future<bool>();
  StreamSubscription<T> subscription =
      this.listen(null, onError: future._completeError, onDone: () {
    future._complete(false);
  }, cancelOnError: true);
  subscription.onData((T element) {
    _runUserCode(() => (element == needle), (bool isMatch) {
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
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/contains.html>
:::
