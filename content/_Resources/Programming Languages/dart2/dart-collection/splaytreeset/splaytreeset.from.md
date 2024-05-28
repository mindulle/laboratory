[dart:collection](../../dart-collection/dart-collection-library){._links-link}

SplayTreeSet\<E\>.from constructor
==================================

::: {.section .multi-line-signature}
SplayTreeSet\<E\>.from(

1.  [Iterable](../../dart-core/iterable-class) elements,
2.  \[[int](../../dart-core/int-class) compare(
    1.  E key1,
    2.  E key2

    )?,
3.  [bool](../../dart-core/bool-class) isValidKey(
    1.  dynamic potentialKey

    )?\]

)
:::

Creates a [SplayTreeSet](../splaytreeset-class) that contains all
`elements`.

The set works as if created by `SplayTreeSet<E>(compare, isValidKey)`.

All the `elements` should be instances of `E` and valid arguments to
`compare`. The `elements` iterable itself may have any element type, so
this constructor can be used to down-cast a `Set`, for example as:

``` {.language-dart data-language="dart"}
Set<SuperType> superSet = ...;
Set<SubType> subSet =
    SplayTreeSet<SubType>.from(superSet.whereType<SubType>());
```

Example:

``` {.language-dart data-language="dart"}
final numbers = <num>[20, 30, 10];
final setFrom = SplayTreeSet<int>.from(numbers);
print(setFrom); // {10, 20, 30}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory SplayTreeSet.from(Iterable elements,
    [int Function(E key1, E key2)? compare,
    bool Function(dynamic potentialKey)? isValidKey]) {
  if (elements is Iterable<E>) {
    return SplayTreeSet<E>.of(elements, compare, isValidKey);
  }
  SplayTreeSet<E> result = SplayTreeSet<E>(compare, isValidKey);
  for (var element in elements) {
    result.add(element as dynamic);
  }
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeSet/SplayTreeSet.from.html>
:::
