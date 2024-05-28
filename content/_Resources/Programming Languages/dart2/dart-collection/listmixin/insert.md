[dart:collection](../../dart-collection/dart-collection-library){._links-link}

insert method
=============

::: {.section .multi-line-signature}
void insert(

1.  [int](../../dart-core/int-class) index,
2.  E element

)

::: {.features}
override
:::
:::

Inserts `element` at position `index` in this list.

This increases the length of the list by one and shifts all objects at
or after the index towards the end of the list.

The list must be growable. The `index` value must be non-negative and no
greater than [length](../../dart-core/list/length).

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 4];
const index = 2;
numbers.insert(index, 10);
print(numbers); // [1, 2, 10, 3, 4]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void insert(int index, E element) {
  checkNotNullable(index, "index");
  var length = this.length;
  RangeError.checkValueInInterval(index, 0, length, "index");
  add(element);
  if (index != length) {
    setRange(index + 1, length + 1, this, index);
    this[index] = element;
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/ListMixin/insert.html>
:::
