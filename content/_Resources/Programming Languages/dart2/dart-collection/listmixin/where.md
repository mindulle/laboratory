[dart:collection](../../dart-collection/dart-collection-library){._links-link}

where method
============

::: {.section .multi-line-signature}
[Iterable](../../dart-core/iterable-class)\<E\> where(

1.  [bool](../../dart-core/bool-class) test(
    1.  E element

    )

)

::: {.features}
override
:::
:::

Returns a new lazy [Iterable](../../dart-core/iterable-class) with all
elements that satisfy the predicate `test`.

The matching elements have the same order in the returned iterable as
they have in [iterator](iterator).

This method returns a view of the mapped elements. As long as the
returned [Iterable](../../dart-core/iterable-class) is not iterated
over, the supplied function `test` will not be invoked. Iterating will
not cache results, and thus iterating multiple times over the returned
[Iterable](../../dart-core/iterable-class) may invoke the supplied
function `test` multiple times on the same element.

Example:

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 5, 6, 7];
var result = numbers.where((x) => x < 5); // (1, 2, 3)
result = numbers.where((x) => x > 5); // (6, 7)
result = numbers.where((x) => x.isEven); // (2, 6)
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Iterable<E> where(bool test(E element)) => WhereIterable<E>(this, test);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/where.html>
:::
