[dart:collection](../../dart-collection/dart-collection-library){._links-link}

intersection method
===================

::: {.section .multi-line-signature}
[Set](../../dart-core/set-class)\<E\> intersection(

1.  [Set](../../dart-core/set-class)\<[Object](../../dart-core/object-class)?\>
    other

)

::: {.features}
override
:::
:::

Creates a new set which is the intersection between this set and
`other`.

That is, the returned set contains all the elements of this
[Set](../../dart-core/set-class) that are also elements of `other`
according to `other.contains`.

``` {.language-dart data-language="dart"}
final characters1 = <String>{'A', 'B', 'C'};
final characters2 = <String>{'A', 'E', 'F'};
final unionSet = characters1.intersection(characters2);
print(unionSet); // {A}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Set<E> intersection(Set<Object?> other) {
  Set<E> result = toSet();
  for (E element in this) {
    if (!other.contains(element)) result.remove(element);
  }
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/SetMixin/intersection.html>
:::
