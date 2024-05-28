[dart:async](../../dart-async/dart-async-library){._links-link}

forEach\<T\> method
===================

::: {.section .multi-line-signature}
[Future](../future-class) forEach\<T\>(

1.  [Iterable](../../dart-core/iterable-class)\<T\> elements,
2.  [FutureOr](../futureor-class) action(
    1.  T element

    )

)
:::

Performs an action for each element of the iterable, in turn.

The `action` may be either synchronous or asynchronous.

Calls `action` with each element in `elements` in order. If the call to
`action` returns a `Future<T>`, the iteration waits until the future is
completed before continuing with the next element.

Returns a [Future](../future-class) that completes with `null` when all
elements have been processed.

Non-[Future](../future-class) return values, and completion-values of
returned [Future](../future-class)s, are discarded.

Any error from `action`, synchronous or asynchronous, will stop the
iteration and be reported in the returned [Future](../future-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Future forEach<T>(Iterable<T> elements, FutureOr action(T element)) {
  var iterator = elements.iterator;
  return doWhile(() {
    if (!iterator.moveNext()) return false;
    var result = action(iterator.current);
    if (result is Future) return result.then(_kTrue);
    return true;
  });
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Future/forEach.html>
:::
