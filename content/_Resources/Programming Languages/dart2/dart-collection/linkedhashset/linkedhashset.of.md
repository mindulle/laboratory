[dart:collection](../../dart-collection/dart-collection-library){._links-link}

LinkedHashSet\<E\>.of constructor
=================================

::: {.section .multi-line-signature}
LinkedHashSet\<E\>.of(

1.  [Iterable](../../dart-core/iterable-class)\<E\> elements

)
:::

Create a linked hash set from `elements`.

Creates a linked hash set as by `LinkedHashSet<E>()` and adds each
element of `elements` to this set in the order they are iterated.
Example:

``` {.language-dart data-language="dart"}
final baseSet = <int>{1, 2, 3};
final setOf = LinkedHashSet<num>.of(baseSet);
print(setOf); // {1, 2, 3}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory LinkedHashSet.of(Iterable<E> elements) =>
    LinkedHashSet<E>()..addAll(elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedHashSet/LinkedHashSet.of.html>
:::
