[dart:async](../../dart-async/dart-async-library){._links-link}

Stream\<T\>.value constructor
=============================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.5\")

</div>

Stream\<T\>.value(

1.  T value

)
:::

Creates a stream which emits a single data event before closing.

This stream emits a single data event of `value` and then closes with a
done event.

Example:

``` {.language-dart data-language="dart"}
Future<void> printThings(Stream<String> data) async {
  await for (var x in data) {
    print(x);
  }
}
printThings(Stream<String>.value('ok')); // prints "ok".
```

The returned stream is effectively equivalent to one created by
`(() async* { yield value; } ())` or
`Future<T>.value(value).asStream()`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.5")
factory Stream.value(T value) =>
    (_AsyncStreamController<T>(null, null, null, null)
          .._add(value)
          .._closeUnchecked())
        .stream;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/Stream.value.html>
:::
