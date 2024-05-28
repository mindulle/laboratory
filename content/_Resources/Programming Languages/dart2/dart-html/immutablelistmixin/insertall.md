[dart:html](../../dart-html/dart-html-library){._links-link}

insertAll method
================

::: {.section .multi-line-signature}
void insertAll(

1.  [int](../../dart-core/int-class) index,
2.  [Iterable](../../dart-core/iterable-class)\<E\> iterable

)

::: {.features}
override
:::
:::

Inserts all objects of `iterable` at position `index` in this list.

This increases the length of the list by the length of `iterable` and
shifts all later objects towards the end of the list.

The list must be growable. The `index` value must be non-negative and no
greater than [length](../../dart-core/list/length).

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 4];
final insertItems = [10, 11];
numbers.insertAll(2, insertItems);
print(numbers); // [1, 2, 10, 11, 3, 4]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void insertAll(int index, Iterable<E> iterable) {
  throw new UnsupportedError("Cannot add to immutable List.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImmutableListMixin/insertAll.html>
:::
