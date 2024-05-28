[dart:core](../../dart-core/dart-core-library){._links-link}

intersection method
===================

::: {.section .multi-line-signature}
[Set](../set-class)\<E\> intersection(

1.  [Set](../set-class)\<[Object](../object-class)?\> other

)
:::

Creates a new set which is the intersection between this set and
`other`.

That is, the returned set contains all the elements of this
[Set](../set-class) that are also elements of `other` according to
`other.contains`.

``` {.language-dart data-language="dart"}
final characters1 = <String>{'A', 'B', 'C'};
final characters2 = <String>{'A', 'E', 'F'};
final unionSet = characters1.intersection(characters2);
print(unionSet); // {A}
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Set<E> intersection(Set<Object?> other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Set/intersection.html>
:::
