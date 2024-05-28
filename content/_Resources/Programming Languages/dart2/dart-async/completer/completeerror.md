[dart:async](../../dart-async/dart-async-library){._links-link}

completeError method
====================

::: {.section .multi-line-signature}
void completeError(

1.  [Object](../../dart-core/object-class) error,
2.  \[[StackTrace](../../dart-core/stacktrace-class)? stackTrace\]

)
:::

Complete [future](future) with an error.

Calling [complete](complete) or [completeError](completeerror) must be
done at most once.

Completing a future with an error indicates that an exception was thrown
while trying to produce a value.

If `error` is a `Future`, the future itself is used as the error value.
If you want to complete with the result of the future, you can use:

``` {.language-dart data-language="dart"}
thisCompleter.complete(theFuture)
```

or if you only want to handle an error from the future:

``` {.language-dart data-language="dart"}
theFuture.catchError(thisCompleter.completeError);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void completeError(Object error, [StackTrace? stackTrace]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Completer/completeError.html>
:::
