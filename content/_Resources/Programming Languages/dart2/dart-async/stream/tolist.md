[dart:async](../../dart-async/dart-async-library){._links-link}

toList method
=============

::: {.section .multi-line-signature}
[Future](../future-class)\<[List](../../dart-core/list-class)\<T\>\>
toList()
:::

Collects all elements of this stream in a `List`.

Creates a `List<T>` and adds all elements of this stream to the list in
the order they arrive. When this stream ends, the returned future is
completed with that list.

If this stream emits an error, the returned future is completed with
that error, and processing stops.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<List<T>> toList() {
  List<T> result = <T>[];
  _Future<List<T>> future = new _Future<List<T>>();
  this.listen(
      (T data) {
        result.add(data);
      },
      onError: future._completeError,
      onDone: () {
        future._complete(result);
      },
      cancelOnError: true);
  return future;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/toList.html>
:::
