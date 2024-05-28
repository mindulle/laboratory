[dart:async](../../dart-async/dart-async-library){._links-link}

errorCallback method
====================

::: {.section .multi-line-signature}
[AsyncError](../asyncerror-class)? errorCallback(

1.  [Object](../../dart-core/object-class) error,
2.  [StackTrace](../../dart-core/stacktrace-class)? stackTrace

)
:::

Intercepts errors when added programmatically to a
[Future](../future-class) or [Stream](../stream-class).

When calling [Completer.completeError](../completer/completeerror),
[StreamController.addError](../streamcontroller/adderror), or some
[Future](../future-class) constructors, the current zone is allowed to
intercept and replace the error.

Future constructors invoke this function when the error is received
directly, for example with [Future.error](../future/future.error), or
when the error is caught synchronously, for example with
[Future.sync](../future/future.sync).

There is no guarantee that an error is only sent through
[errorCallback](errorcallback) once. Libraries that use intermediate
controllers or completers might end up invoking
[errorCallback](errorcallback) multiple times.

Returns `null` if no replacement is desired. Otherwise returns an
instance of [AsyncError](../asyncerror-class) holding the new pair of
error and stack trace.

Custom zones may intercept this operation.

Implementations of a new asynchronous primitive that converts
synchronous errors to asynchronous errors rarely need to invoke
[errorCallback](errorcallback), since errors are usually reported
through future completers or stream controllers.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
AsyncError? errorCallback(Object error, StackTrace? stackTrace);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Zone/errorCallback.html>
:::
