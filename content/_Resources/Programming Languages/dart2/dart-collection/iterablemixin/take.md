[dart:collection](../../dart-collection/dart-collection-library){._links-link}

take method
===========

::: {.section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<E\> take(

1.  [int](../../dart-core/int-class) count

)

::: {.features}
override
:::
:::

Returns a lazy iterable of the `count` first elements of this iterable.

The returned `Iterable` may contain fewer than `count` elements, if
`this` contains fewer than `count` elements.

The elements can be computed by stepping through
[iterator](../../dart-core/iterable/iterator) until `count` elements
have been seen.

The `count` must not be negative.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 5, 6, 7];
final result = numbers.take(4); // (1, 2, 3, 5)
final takeAll = numbers.take(100); // (1, 2, 3, 5, 6, 7)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<E> take(int count) {
  return TakeIterable<E>(this, count);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/IterableMixin/take.html>
:::
