[dart:collection](../../dart-collection/dart-collection-library){._links-link}

skipWhile method
================

::: {.section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<E\> skipWhile(

1.  [bool](../../dart-core/bool-class) test(
    1.  E element

    )

)

::: {.features}
inherited
:::
:::

Returns an `Iterable` that skips leading elements while `test` is
satisfied.

The filtering happens lazily. Every new
[Iterator](../../dart-core/iterator-class) of the returned iterable
iterates over all elements of `this`.

The returned iterable provides elements by iterating this iterable, but
skipping over all initial elements where `test(element)` returns true.
If all elements satisfy `test` the resulting iterable is empty,
otherwise it iterates the remaining elements in their original order,
starting with the first element for which `test(element)` returns
`false`.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 5, 6, 7];
var result = numbers.skipWhile((x) => x < 5); // (5, 6, 7)
result = numbers.skipWhile((x) => x != 3); // (3, 5, 6, 7)
result = numbers.skipWhile((x) => x != 4); // ()
result = numbers.skipWhile((x) => x.isOdd); // (2, 3, 5, 6, 7)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<E> skipWhile(bool test(E element)) => super.skipWhile(test);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListQueue/skipWhile.html>
:::
