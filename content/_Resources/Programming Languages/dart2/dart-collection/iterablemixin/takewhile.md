[dart:collection](../../dart-collection/dart-collection-library){._links-link}

takeWhile method
================

::: {.section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<E\> takeWhile(

1.  [bool](../../dart-core/bool-class) test(
    1.  E value

    )

)

::: {.features}
override
:::
:::

Returns a lazy iterable of the leading elements satisfying `test`.

The filtering happens lazily. Every new iterator of the returned
iterable starts iterating over the elements of `this`.

The elements can be computed by stepping through
[iterator](../../dart-core/iterable/iterator) until an element is found
where `test(element)` is false. At that point, the returned iterable
stops (its `moveNext()` returns false).

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 5, 6, 7];
var result = numbers.takeWhile((x) => x < 5); // (1, 2, 3)
result = numbers.takeWhile((x) => x != 3); // (1, 2)
result = numbers.takeWhile((x) => x != 4); // (1, 2, 3, 5, 6, 7)
result = numbers.takeWhile((x) => x.isOdd); // (1)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<E> takeWhile(bool test(E value)) {
  return TakeWhileIterable<E>(this, test);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/IterableMixin/takeWhile.html>
:::
