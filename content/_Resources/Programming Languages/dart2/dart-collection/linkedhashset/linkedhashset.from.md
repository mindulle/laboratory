[dart:collection](../../dart-collection/dart-collection-library){._links-link}

LinkedHashSet\<E\>.from constructor
===================================

::: {.section .multi-line-signature}
LinkedHashSet\<E\>.from(

1.  [Iterable](../../dart-core/iterable-class) elements

)
:::

Create a linked hash set containing all `elements`.

Creates a linked hash set as by `LinkedHashSet<E>()` and adds each
element of `elements` to this set in the order they are iterated.

All the `elements` should be instances of `E`. The `elements` iterable
itself may have any element type, so this constructor can be used to
down-cast a `Set`, for example as:

``` {.language-dart data-language="dart"}
Set<SuperType> superSet = ...;
Iterable<SuperType> tmp = superSet.where((e) => e is SubType);
Set<SubType> subSet = LinkedHashSet<SubType>.from(tmp);
```

Example:

``` {.language-dart data-language="dart"}
final numbers = <num>[10, 20, 30];
final setFrom = LinkedHashSet<int>.from(numbers);
print(setFrom); // {10, 20, 30}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory LinkedHashSet.from(Iterable<dynamic> elements) {
  LinkedHashSet<E> result = LinkedHashSet<E>();
  for (final element in elements) {
    result.add(element as E);
  }
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/LinkedHashSet/LinkedHashSet.from.html>
:::
