[dart:core](../../dart-core/dart-core-library){._links-link}

throwWithStackTrace method
==========================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.16\")

</div>

Never throwWithStackTrace(

1.  [Object](../object-class) error,
2.  [StackTrace](../stacktrace-class) stackTrace

)

::: {.features}
\@Since(\"2.16\")
:::
:::

Throws `error` with associated stack trace `stackTrace`.

Behaves like `throw error` would if the
[StackTrace.current](../stacktrace/current) was `stackTrace` at the time
of the `throw`.

Like for a `throw`, if `error` extends [Error](../error-class), and it
has not been thrown before, its [Error.stackTrace](stacktrace) property
will be set to the `stackTrace`.

This function does not guarantee to preserve the identity of
`stackTrace`. The [StackTrace](../stacktrace-class) object that is
caught by a `try`/`catch` of this error, or which is set as the
[Error.stackTrace](stacktrace) of an `error`, may not be the same
`stackTrace` object provided as argument, but it will have the same
contents according to [StackTrace.toString](../stacktrace/tostring).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.16")
static Never throwWithStackTrace(Object error, StackTrace stackTrace) {
  checkNotNullable(error, "error");
  checkNotNullable(stackTrace, "stackTrace");
  _throw(error, stackTrace);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Error/throwWithStackTrace.html>
:::
