[dart:async](../../dart-async/dart-async-library){._links-link}

Future\<T\>.value constructor
=============================

::: {.section .multi-line-signature}
Future\<T\>.value(

1.  \[[FutureOr](../futureor-class)\<T\>? value\]

)
:::

Creates a future completed with `value`.

If `value` is a future, the created future waits for the `value` future
to complete, and then completes with the same result. Since a `value`
future can complete with an error, so can the future created by
[Future.value](future.value), even if the name suggests otherwise.

If `value` is not a [Future](../future-class), the created future is
completed with the `value` value, equivalently to
`new Future<T>.sync(() => value)`.

If `value` is omitted or `null`, it is converted to `FutureOr<T>` by
`value as FutureOr<T>`. If `T` is not nullable, then a non-`null`
`value` must be provided, otherwise the construction throws.

Use [Completer](../completer-class) to create a future now and complete
it later.

Example:

``` {.language-dart data-language="dart"}
Future<int> getFuture() {
 return Future<int>.value(2021);
}

final result = await getFuture();
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
@pragma("vm:prefer-inline")
factory Future.value([FutureOr<T>? value]) {
  return new _Future<T>.immediate(value == null ? value as T : value);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/Future.value.html>
:::
