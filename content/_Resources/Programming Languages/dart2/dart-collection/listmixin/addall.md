[dart:collection](../../dart-collection/dart-collection-library){._links-link}

addAll method
=============

::: {.section .multi-line-signature}
void addAll(

1.  [Iterable](../../dart-core/iterable-class)\<E\> iterable

)

::: {.features}
override
:::
:::

Appends all objects of `iterable` to the end of this list.

Extends the length of the list by the number of objects in `iterable`.
The list must be growable.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
numbers.addAll([4, 5, 6]);
print(numbers); // [1, 2, 3, 4, 5, 6]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addAll(Iterable<E> iterable) {
  int i = this.length;
  for (E element in iterable) {
    assert(this.length == i || (throw ConcurrentModificationError(this)));
    add(element);
    i++;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/addAll.html>
:::
