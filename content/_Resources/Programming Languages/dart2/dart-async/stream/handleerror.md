[dart:async](../../dart-async/dart-async-library){._links-link}

handleError method
==================

::: {.section .multi-line-signature}
[Stream](../stream-class)\<T\> handleError(

1.  [Function](../../dart-core/function-class) onError,
2.  {[bool](../../dart-core/bool-class) test(
    1.  dynamic error

    )?}

)
:::

Creates a wrapper Stream that intercepts some errors from this stream.

If this stream sends an error that matches `test`, then it is
intercepted by the `onError` function.

The `onError` callback must be of type `void Function(Object error)` or
`void Function(Object error, StackTrace)`. The function type determines
whether `onError` is invoked with a stack trace argument. The stack
trace argument may be
[StackTrace.empty](../../dart-core/stacktrace/empty-constant) if this
stream received an error without a stack trace.

An asynchronous error `error` is matched by a test function if
`test(error)` returns true. If `test` is omitted, every error is
considered matching.

If the error is intercepted, the `onError` function can decide what to
do with it. It can throw if it wants to raise a new (or the same) error,
or simply return to make this stream forget the error. If the received
`error` value is thrown again by the `onError` function, it acts like a
`rethrow` and it is emitted along with its original stack trace, not the
stack trace of the `throw` inside `onError`.

If you need to transform an error into a data event, use the more
generic [Stream.transform](transform) to handle the event by writing a
data event to the output sink.

The returned stream is a broadcast stream if this stream is. If a
broadcast stream is listened to more than once, each subscription will
individually perform the `test` and handle the error.

Example:

``` {.language-dart data-language="dart"}
Stream.periodic(const Duration(seconds: 1), (count) {
  if (count == 2) {
    throw Exception('Exceptional event');
  }
  return count;
}).take(4).handleError(print).forEach(print);

// Outputs:
// 0
// 1
// Exception: Exceptional event
// 3
// 4
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Stream<T> handleError(Function onError, {bool test(error)?}) {
  final void Function(Object, StackTrace) callback;
  if (onError is void Function(Object, StackTrace)) {
    callback = onError;
  } else if (onError is void Function(Object)) {
    callback = (Object error, StackTrace _) {
      onError(error);
    };
  } else {
    throw ArgumentError.value(
        onError,
        "onError",
        "Error handler must accept one Object or one Object and a StackTrace"
            " as arguments.");
  }
  return new _HandleErrorStream<T>(this, callback, test);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/handleError.html>
:::
