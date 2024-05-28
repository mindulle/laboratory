[dart:core](../../dart-core/dart-core-library){._links-link}

StackTrace.fromString constructor
=================================

::: {.section .multi-line-signature}
StackTrace.fromString(

1.  [String](../string-class) stackTraceString

)
:::

Create a `StackTrace` object from `stackTraceString`.

The created stack trace will have a `toString` method returning
`stackTraceString`.

The `stackTraceString` can be a string returned by some other stack
trace, or it can be any string at all. If the string doesn\'t look like
a stack trace, code that interprets stack traces is likely to fail, so
fake stack traces should be used with care.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory StackTrace.fromString(String stackTraceString) = _StringStackTrace;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/StackTrace/StackTrace.fromString.html>
:::
