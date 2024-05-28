[dart:async](../../dart-async/dart-async-library){._links-link}

any\<T\> method
===============

::: {.section .multi-line-signature}
[Future](../future-class)\<T\> any\<T\>(

1.  [Iterable](../../dart-core/iterable-class)\<[Future](../future-class)\<T\>\>
    futures

)
:::

Returns the result of the first future in `futures` to complete.

The returned future is completed with the result of the first future in
`futures` to report that it is complete, whether it\'s with a value or
an error. The results of all the other futures are discarded.

If `futures` is empty, or if none of its futures complete, the returned
future never completes.

Example:

``` {.language-dart data-language="dart"}
void main() async {
  final result =
      await Future.any([slowInt(), delayedString(), fastInt()]);
  // The future of fastInt completes first, others are ignored.
  print(result); // 3
}
Future<int> slowInt() async {
  await Future.delayed(const Duration(seconds: 2));
  return 2;
}

Future<String> delayedString() async {
  await Future.delayed(const Duration(seconds: 2));
  throw TimeoutException('Time has passed');
}

Future<int> fastInt() async {
  await Future.delayed(const Duration(seconds: 1));
  return 3;
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future<T> any<T>(Iterable<Future<T>> futures) {
  var completer = new Completer<T>.sync();
  void onValue(T value) {
    if (!completer.isCompleted) completer.complete(value);
  }

  void onError(Object error, StackTrace stack) {
    if (!completer.isCompleted) completer.completeError(error, stack);
  }

  for (var future in futures) {
    future.then(onValue, onError: onError);
  }
  return completer.future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/any.html>
:::
