[dart:async](../../dart-async/dart-async-library){._links-link}

Future\<T\>.error constructor
=============================

::: {.section .multi-line-signature}
Future\<T\>.error(

1.  [Object](../../dart-core/object-class) error,
2.  \[[StackTrace](../../dart-core/stacktrace-class)? stackTrace\]

)
:::

Creates a future that completes with an error.

The created future will be completed with an error in a future
microtask. This allows enough time for someone to add an error handler
on the future. If an error handler isn\'t added before the future
completes, the error will be considered unhandled.

Use [Completer](../completer-class) to create a future and complete it
later.

Example:

``` {.language-dart data-language="dart"}
Future<int> getFuture() {
 return Future.error(Exception('Issue'));
}

final error = await getFuture(); // Throws.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Future.error(Object error, [StackTrace? stackTrace]) {
  // TODO(40614): Remove once non-nullability is sound.
  checkNotNullable(error, "error");
  if (!identical(Zone.current, _rootZone)) {
    AsyncError? replacement = Zone.current.errorCallback(error, stackTrace);
    if (replacement != null) {
      error = replacement.error;
      stackTrace = replacement.stackTrace;
    }
  }
  stackTrace ??= AsyncError.defaultStackTrace(error);
  return new _Future<T>.immediateError(error, stackTrace);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/Future.error.html>
:::
