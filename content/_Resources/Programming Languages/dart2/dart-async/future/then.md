[dart:async](../../dart-async/dart-async-library){._links-link}

then\<R\> method
================

::: {.section .multi-line-signature}
[Future](../future-class)\<R\> then\<R\>(

1.  [FutureOr](../futureor-class)\<R\> onValue(
    1.  T value

    ),
2.  {[Function](../../dart-core/function-class)? onError}

)
:::

Register callbacks to be called when this future completes.

When this future completes with a value, the `onValue` callback will be
called with that value. If this future is already completed, the
callback will not be called immediately, but will be scheduled in a
later microtask.

If `onError` is provided, and this future completes with an error, the
`onError` callback is called with that error and its stack trace. The
`onError` callback must accept either one argument or two arguments
where the latter is a [StackTrace](../../dart-core/stacktrace-class). If
`onError` accepts two arguments, it is called with both the error and
the stack trace, otherwise it is called with just the error object. The
`onError` callback must return a value or future that can be used to
complete the returned future, so it must be something assignable to
`FutureOr<R>`.

Returns a new [Future](../future-class) which is completed with the
result of the call to `onValue` (if this future completes with a value)
or to `onError` (if this future completes with an error).

If the invoked callback throws, the returned future is completed with
the thrown error and a stack trace for the error. In the case of
`onError`, if the exception thrown is `identical` to the error argument
to `onError`, the throw is considered a rethrow, and the original stack
trace is used instead.

If the callback returns a [Future](../future-class), the future returned
by `then` will be completed with the same result as the future returned
by the callback.

If `onError` is not given, and this future completes with an error, the
error is forwarded directly to the returned future.

In most cases, it is more readable to use [catchError](catcherror)
separately, possibly with a `test` parameter, instead of handling both
value and error in a single [then](then) call.

Note that futures don\'t delay reporting of errors until listeners are
added. If the first `then` or `catchError` call happens after this
future has completed with an error, then the error is reported as
unhandled error. See the description on [Future](../future-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<R> then<R>(FutureOr<R> onValue(T value), {Function? onError});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/then.html>
:::
