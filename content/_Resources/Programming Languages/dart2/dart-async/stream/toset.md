[dart:async](../../dart-async/dart-async-library){._links-link}

toSet method
============

::: {.section .multi-line-signature}
[Future](../future-class)\<[Set](../../dart-core/set-class)\<T\>\>
toSet()
:::

Collects the data of this stream in a `Set`.

Creates a `Set<T>` and adds all elements of this stream to the set. in
the order they arrive. When this stream ends, the returned future is
completed with that set.

The returned set is the same type as created by `<T>{}`. If another type
of set is needed, either use [forEach](foreach) to add each element to
the set, or use `toList().then((list) => new SomeOtherSet.from(list))`
to create the set.

If this stream emits an error, the returned future is completed with
that error, and processing stops.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<Set<T>> toSet() {
  Set<T> result = new Set<T>();
  _Future<Set<T>> future = new _Future<Set<T>>();
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
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/toSet.html>
:::
