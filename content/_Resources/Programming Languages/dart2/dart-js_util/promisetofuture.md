[dart:js\_util](../dart-js_util/dart-js_util-library){._links-link}

promiseToFuture\<T\> function
=============================

::: {.section .multi-line-signature}
[Future](../dart-async/future-class)\<T\> promiseToFuture\<T\>(

1.  [Object](../dart-core/object-class) jsPromise

)
:::

Converts a JavaScript Promise to a Dart
[Future](../dart-async/future-class).

``` {.language-dart data-language="dart"}
@JS()
external Promise<num> get threePromise; // Resolves to 3

void main() async {
  final Future<num> threeFuture = promiseToFuture(threePromise);

  final three = await threeFuture; // == 3
}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external Future<T> promiseToFuture<T>(Object jsPromise);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js_util/promiseToFuture.html>
:::
