[dart:collection](../../dart-collection/dart-collection-library){._links-link}

union method
============

::: {.section .multi-line-signature}
[Set](../../dart-core/set-class)\<E\> union(

1.  [Set](../../dart-core/set-class)\<E\> other

)

::: {.features}
override
:::
:::

Creates a new set which contains all the elements of this set and
`other`.

That is, the returned set contains all the elements of this
[Set](../../dart-core/set-class) and all the elements of `other`.

``` {.language-dart data-language="dart"}
final characters1 = <String>{'A', 'B', 'C'};
final characters2 = <String>{'A', 'E', 'F'};
final unionSet1 = characters1.union(characters2);
print(unionSet1); // {A, B, C, E, F}
final unionSet2 = characters2.union(characters1);
print(unionSet2); // {A, E, F, B, C}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Set<E> union(Set<E> other) {
  return _clone()..addAll(other);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SplayTreeSet/union.html>
:::
