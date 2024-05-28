[dart:async](../../dart-async/dart-async-library){._links-link}

onError\<E extends Object\> method
==================================

::: {.section .multi-line-signature}
[Future](../future-class)\<T\> onError\<E extends Object\>(

1.  [FutureOr](../futureor-class)\<T\> handleError(
    1.  E error,
    2.  [StackTrace](../../dart-core/stacktrace-class) stackTrace

    ),
2.  {[bool](../../dart-core/bool-class) test(
    1.  E error

    )?}

)
:::

Handles errors on this future.

Catches errors of type `E` that this future complete with. If `test` is
supplied, only catches errors of type `E` where `test` returns `true`.
If `E` is [Object](../../dart-core/object-class), then all errors are
potentially caught, depending only on a supplied `test`.toString()

If the error is caught, the returned future completes with the result of
calling `handleError` with the error and stack trace. This result must
be a value of the same type that this future could otherwise complete
with. For example, if this future cannot complete with `null`, then
`handleError` also cannot return `null`. Example:

``` {.language-dart data-language="dart"}
Future<T> retryOperation<T>(Future<T> operation(), T onFailure()) =>
    operation().onError<RetryException>((e, s) {
      if (e.canRetry) {
        return retryOperation(operation, onFailure);
      }
      return onFailure();
    });
```

If `handleError` throws, the returned future completes with the thrown
error and stack trace, except that if it throws the *same* error object
again, then it is considered a \"rethrow\" and the original stack trace
is retained. This can be used as an alternative to skipping the error in
`test`. Example:

``` {.language-dart data-language="dart"}
// Unwraps an an exceptions cause, if it has one.
someFuture.onError<SomeException>((e, _) {
  throw e.cause ?? e;
});
// vs.
someFuture.onError<SomeException>((e, _) {
  throw e.cause!;
}, test: (e) => e.cause != null);
```

If the error is not caught, the returned future completes with the same
result, value or error, as this future.

This method is effectively a more precisely typed version of
[Future.catchError](../future/catcherror). It makes it easy to catch
specific error types, and requires a correctly typed error handler
function, rather than just [Function](../../dart-core/function-class).
Because of this, the error handlers must accept the stack trace
argument.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<T> onError<E extends Object>(
    FutureOr<T> handleError(E error, StackTrace stackTrace),
    {bool test(E error)?}) {
  // There are various ways to optimize this to avoid the double is E/as E
  // type check, but for now we are not optimizing the error path.
  return this.catchError(
      (Object error, StackTrace stackTrace) =>
          handleError(error as E, stackTrace),
      test: (Object error) => error is E && (test == null || test(error)));
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/FutureExtensions/onError.html>
:::
