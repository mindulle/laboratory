[dart:core](../../dart-core/dart-core-library){._links-link}

setAll method
=============

::: {.section .multi-line-signature}
void setAll(

1.  [int](../int-class) index,
2.  [Iterable](../iterable-class)\<E\> iterable

)
:::

Overwrites elements with the objects of `iterable`.

The elements of `iterable` are written into this list, starting at
position `index`. This operation does not increase the length of the
list.

The `index` must be non-negative and no greater than [length](length).

The `iterable` must not have more elements than what can fit from
`index` to [length](length).

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
void setAll(int index, Iterable<E> iterable);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/setAll.html>
:::
