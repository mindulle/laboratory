[dart:collection](../../dart-collection/dart-collection-library){._links-link}

difference method
=================

::: {.section .multi-line-signature}
[Set](../../dart-core/set-class)\<E\> difference(

1.  [Set](../../dart-core/set-class)\<[Object](../../dart-core/object-class)?\>
    other

)

::: {.features}
override
:::
:::

Creates a new set with the elements of this that are not in `other`.

That is, the returned set contains all the elements of this
[Set](../../dart-core/set-class) that are not elements of `other`
according to `other.contains`.

``` {.language-dart data-language="dart"}
final characters1 = <String>{'A', 'B', 'C'};
final characters2 = <String>{'A', 'E', 'F'};
final differenceSet1 = characters1.difference(characters2);
print(differenceSet1); // {B, C}
final differenceSet2 = characters2.difference(characters1);
print(differenceSet2); // {E, F}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Set<E> difference(Set<Object?> other) {
  Set<E> result = toSet();
  for (E element in this) {
    if (other.contains(element)) result.remove(element);
  }
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/difference.html>
:::
