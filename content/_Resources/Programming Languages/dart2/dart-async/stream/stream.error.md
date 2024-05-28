[dart:async](../../dart-async/dart-async-library){._links-link}

Stream\<T\>.error constructor
=============================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.5\")

</div>

Stream\<T\>.error(

1.  [Object](../../dart-core/object-class) error,
2.  \[[StackTrace](../../dart-core/stacktrace-class)? stackTrace\]

)
:::

Creates a stream which emits a single error event before completing.

This stream emits a single error event of `error` and `stackTrace` and
then completes with a done event.

Example:

``` {.language-dart data-language="dart"}
Future<void> tryThings(Stream<int> data) async {
  try {
    await for (var x in data) {
      print('Data: $x');
    }
  } catch (e) {
    print(e);
  }
}
tryThings(Stream<int>.error('Error')); // prints "Error".
```

The returned stream is effectively equivalent to one created by
`Future<T>.error(error, stackTrace).asStream()`, by or
`(() async* { throw error; } ())`, except that you can control the stack
trace as well.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.5")
factory Stream.error(Object error, [StackTrace? stackTrace]) {
  // TODO(40614): Remove once non-nullability is sound.
  checkNotNullable(error, "error");
  return (_AsyncStreamController<T>(null, null, null, null)
        .._addError(error, stackTrace ?? AsyncError.defaultStackTrace(error))
        .._closeUnchecked())
      .stream;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/Stream.error.html>
:::
