[dart:collection](../../dart-collection/dart-collection-library){._links-link}

HashSet\<E\>.of constructor
===========================

::: {.section .multi-line-signature}
HashSet\<E\>.of(

1.  [Iterable](../../dart-core/iterable-class)\<E\> elements

)
:::

Create a hash set containing all `elements`.

Creates a hash set as by `HashSet<E>()` and adds all given `elements` to
the set. The elements are added in order. If `elements` contains two
entries that are equal, but not identical, then the first one is the one
in the resulting set. Example:

``` {.language-dart data-language="dart"}
final baseSet = <int>{1, 2, 3};
final hashSetOf = HashSet<num>.of(baseSet);
print(hashSetOf); // fx {3, 1, 2}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HashSet.of(Iterable<E> elements) => HashSet<E>()..addAll(elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashSet/HashSet.of.html>
:::
