[dart:async](../../dart-async/dart-async-library){._links-link}

defaultStackTrace method
========================

::: {.section .multi-line-signature}
[StackTrace](../../dart-core/stacktrace-class) defaultStackTrace(

1.  [Object](../../dart-core/object-class) error

)
:::

A default stack trace for an error.

If `error` is an [Error](../../dart-core/error-class) and it has an
[Error.stackTrace](../../dart-core/error/stacktrace), that stack trace
is returned. If not, the
[StackTrace.empty](../../dart-core/stacktrace/empty-constant) default
stack trace is returned.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static StackTrace defaultStackTrace(Object error) {
  if (error is Error) {
    var stackTrace = error.stackTrace;
    if (stackTrace != null) return stackTrace;
  }
  return StackTrace.empty;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/AsyncError/defaultStackTrace.html>
:::
