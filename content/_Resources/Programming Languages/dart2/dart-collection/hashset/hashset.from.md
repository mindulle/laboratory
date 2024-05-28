[dart:collection](../../dart-collection/dart-collection-library){._links-link}

HashSet\<E\>.from constructor
=============================

::: {.section .multi-line-signature}
HashSet\<E\>.from(

1.  [Iterable](../../dart-core/iterable-class) elements

)
:::

Create a hash set containing all `elements`.

Creates a hash set as by `HashSet<E>()` and adds all given `elements` to
the set. The elements are added in order. If `elements` contains two
entries that are equal, but not identical, then the first one is the one
in the resulting set.

All the `elements` should be instances of `E`. The `elements` iterable
itself may have any element type, so this constructor can be used to
down-cast a `Set`, for example as:

``` {.language-dart data-language="dart"}
Set<SuperType> superSet = ...;
Set<SubType> subSet =
    HashSet<SubType>.from(superSet.whereType<SubType>());
```

Example:

``` {.language-dart data-language="dart"}
final numbers = <num>[10, 20, 30];
final hashSetFrom = HashSet<int>.from(numbers);
print(hashSetFrom); // fx {20, 10, 30}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory HashSet.from(Iterable<dynamic> elements) {
  HashSet<E> result = HashSet<E>();
  for (final e in elements) {
    result.add(e as E);
  }
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/HashSet/HashSet.from.html>
:::
