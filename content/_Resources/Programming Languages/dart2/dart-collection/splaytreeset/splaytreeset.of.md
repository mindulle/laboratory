[dart:collection](../../dart-collection/dart-collection-library){._links-link}

SplayTreeSet\<E\>.of constructor
================================

::: {.section .multi-line-signature}
SplayTreeSet\<E\>.of(

1.  [Iterable](../../dart-core/iterable-class)\<E\> elements,
2.  \[[int](../../dart-core/int-class) compare(
    1.  E key1,
    2.  E key2

    )?,
3.  [bool](../../dart-core/bool-class) isValidKey(
    1.  dynamic potentialKey

    )?\]

)
:::

Creates a [SplayTreeSet](../splaytreeset-class) from `elements`.

The set works as if created by
`new SplayTreeSet<E>(compare, isValidKey)`.

All the `elements` should be valid as arguments to the `compare`
function. Example:

``` {.language-dart data-language="dart"}
final baseSet = <int>{1, 2, 3};
final setOf = SplayTreeSet<num>.of(baseSet);
print(setOf); // {1, 2, 3}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SplayTreeSet.of(Iterable<E> elements,
        [int Function(E key1, E key2)? compare,
        bool Function(dynamic potentialKey)? isValidKey]) =>
    SplayTreeSet(compare, isValidKey)..addAll(elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeSet/SplayTreeSet.of.html>
:::
