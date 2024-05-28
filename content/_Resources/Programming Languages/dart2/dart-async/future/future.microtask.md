[dart:async](../../dart-async/dart-async-library){._links-link}

Future\<T\>.microtask constructor
=================================

::: {.section .multi-line-signature}
Future\<T\>.microtask(

1.  [FutureOr](../futureor-class)\<T\> computation( )

)
:::

Creates a future containing the result of calling `computation`
asynchronously with [scheduleMicrotask](../schedulemicrotask).

If executing `computation` throws, the returned future is completed with
the thrown error.

If calling `computation` returns a [Future](../future-class), completion
of the created future will wait until the returned future completes, and
will then complete with the same result.

If calling `computation` returns a non-future value, the returned future
is completed with that value.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Future.microtask(FutureOr<T> computation()) {
  _Future<T> result = new _Future<T>();
  scheduleMicrotask(() {
    try {
      result._complete(computation());
    } catch (e, s) {
      _completeWithErrorCallback(result, e, s);
    }
  });
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/Future.microtask.html>
:::
