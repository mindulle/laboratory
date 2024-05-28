[dart:core](../../dart-core/dart-core-library){._links-link}

stackTrace property
===================

::: {#getter .section .multi-line-signature}
[StackTrace](../stacktrace-class)? stackTrace

::: {.features}
override
:::
:::

The stack trace at the point where this error was first thrown.

Classes which *extend* `Error` will automatically have a stack trace
filled in the first time they are thrown by a `throw` expression.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
StackTrace? get stackTrace => null;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/StackOverflowError/stackTrace.html>
:::
