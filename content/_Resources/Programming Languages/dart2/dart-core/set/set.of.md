[dart:core](../../dart-core/dart-core-library){._links-link}

Set\<E\>.of constructor
=======================

::: {.section .multi-line-signature}
Set\<E\>.of(

1.  [Iterable](../iterable-class)\<E\> elements

)
:::

Creates a [Set](../set-class) from `elements`.

The created [Set](../set-class) is a
[LinkedHashSet](../../dart-collection/linkedhashset-class). As such, it
considers elements that are equal (using [operator
==](../object/operator_equals)) to be indistinguishable, and requires
them to have a compatible [Object.hashCode](../object/hashcode)
implementation.

The set is equivalent to one created by `LinkedHashSet<E>.of(elements)`.

``` {.language-dart data-language="dart"}
final baseSet = <int>{1, 2, 3};
final setOf = Set<num>.of(baseSet);
print(setOf); // {1, 2, 3}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Set.of(Iterable<E> elements) = LinkedHashSet<E>.of;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Set/Set.of.html>
:::
