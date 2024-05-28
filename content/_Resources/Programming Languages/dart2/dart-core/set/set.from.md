[dart:core](../../dart-core/dart-core-library){._links-link}

Set\<E\>.from constructor
=========================

::: {.section .multi-line-signature}
Set\<E\>.from(

1.  [Iterable](../iterable-class) elements

)
:::

Creates a [Set](../set-class) that contains all `elements`.

All the `elements` should be instances of `E`. The `elements` iterable
itself can have any type, so this constructor can be used to down-cast a
`Set`, for example as:

``` {.language-dart data-language="dart"}
Set<SuperType> superSet = ...;
Set<SubType> subSet =
    Set<SubType>.from(superSet.where((e) => e is SubType));
```

The created [Set](../set-class) is a
[LinkedHashSet](../../dart-collection/linkedhashset-class). As such, it
considers elements that are equal (using [operator
==](../object/operator_equals)) to be indistinguishable, and requires
them to have a compatible [Object.hashCode](../object/hashcode)
implementation.

The set is equivalent to one created by
`LinkedHashSet<E>.from(elements)`.

``` {.language-dart data-language="dart"}
final numbers = <num>{10, 20, 30};
final setFrom = Set<int>.from(numbers);
print(setFrom); // {10, 20, 30}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Set.from(Iterable elements) = LinkedHashSet<E>.from;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Set/Set.from.html>
:::
