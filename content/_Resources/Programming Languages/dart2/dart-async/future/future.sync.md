[dart:async](../../dart-async/dart-async-library){._links-link}

Future\<T\>.sync constructor
============================

::: {.section .multi-line-signature}
Future\<T\>.sync(

1.  [FutureOr](../futureor-class)\<T\> computation( )

)
:::

Returns a future containing the result of immediately calling
`computation`.

If calling `computation` throws, the returned future is completed with
the error.

If calling `computation` returns a `Future<T>`, that future is returned.

If calling `computation` returns a non-future value, a future is
returned which has been completed with that value.

Example:

``` {.language-dart data-language="dart"}
final result = await Future<int>.sync(() => 12);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Future.sync(FutureOr<T> computation()) {
  try {
    var result = computation();
    if (result is Future<T>) {
      return result;
    } else {
      // TODO(40014): Remove cast when type promotion works.
      return new _Future<T>.value(result as dynamic);
    }
  } catch (error, stackTrace) {
    var future = new _Future<T>();
    AsyncError? replacement = Zone.current.errorCallback(error, stackTrace);
    if (replacement != null) {
      future._asyncCompleteError(replacement.error, replacement.stackTrace);
    } else {
      future._asyncCompleteError(error, stackTrace);
    }
    return future;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/Future.sync.html>
:::
