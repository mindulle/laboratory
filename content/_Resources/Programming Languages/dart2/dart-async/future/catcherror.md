[dart:async](../../dart-async/dart-async-library){._links-link}

catchError method
=================

::: {.section .multi-line-signature}
[Future](../future-class)\<T\> catchError(

1.  [Function](../../dart-core/function-class) onError,
2.  {[bool](../../dart-core/bool-class) test(
    1.  [Object](../../dart-core/object-class) error

    )?}

)
:::

Handles errors emitted by this [Future](../future-class).

This is the asynchronous equivalent of a \"catch\" block.

Returns a new [Future](../future-class) that will be completed with
either the result of this future or the result of calling the `onError`
callback.

If this future completes with a value, the returned future completes
with the same value.

If this future completes with an error, then `test` is first called with
the error value.

If `test` returns false, the exception is not handled by this
`catchError`, and the returned future completes with the same error and
stack trace as this future.

If `test` returns `true`, `onError` is called with the error and
possibly stack trace, and the returned future is completed with the
result of this call in exactly the same way as for [then](then)\'s
`onError`.

If `test` is omitted, it defaults to a function that always returns
true. The `test` function should not throw, but if it does, it is
handled as if the `onError` function had thrown.

Note that futures don\'t delay reporting of errors until listeners are
added. If the first `catchError` (or `then`) call happens after this
future has completed with an error then the error is reported as
unhandled error. See the description on [Future](../future-class).

Example:

``` {.language-dart data-language="dart"}
Future.delayed(
  const Duration(seconds: 1),
  () => throw 401,
).then((value) {
  throw 'Unreachable';
}).catchError((err) {
  print('Error: $err'); // Prints 401.
}, test: (error) {
  return error is int && error >= 400;
});
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
// The `Function` below stands for one of two types:
// - (dynamic) -> FutureOr<T>
// - (dynamic, StackTrace) -> FutureOr<T>
// Given that there is a `test` function that is usually used to do an
// `is` check, we should also expect functions that take a specific argument.
Future<T> catchError(Function onError, {bool test(Object error)?});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/catchError.html>
:::
