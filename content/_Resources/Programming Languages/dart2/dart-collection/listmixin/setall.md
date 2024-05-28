[dart:collection](../../dart-collection/dart-collection-library){._links-link}

setAll method
=============

::: {.section .multi-line-signature}
void setAll(

1.  [int](../../dart-core/int-class) index,
2.  [Iterable](../../dart-core/iterable-class)\<E\> iterable

)

::: {.features}
override
:::
:::

Overwrites elements with the objects of `iterable`.

The elements of `iterable` are written into this list, starting at
position `index`. This operation does not increase the length of the
list.

The `index` must be non-negative and no greater than
[length](../../dart-core/list/length).

The `iterable` must not have more elements than what can fit from
`index` to [length](../../dart-core/list/length).

If `iterable` is based on this list, its values may change *during* the
`setAll` operation.

``` {.language-dart data-language="dart"}
final list = <String>['a', 'b', 'c', 'd'];
list.setAll(1, ['bee', 'sea']);
print(list); // [a, bee, sea, d]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setAll(int index, Iterable<E> iterable) {
  if (iterable is List) {
    setRange(index, index + iterable.length, iterable);
  } else {
    for (E element in iterable) {
      this[index++] = element;
    }
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/setAll.html>
:::
