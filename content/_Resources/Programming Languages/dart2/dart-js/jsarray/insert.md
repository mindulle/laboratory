[dart:js](../../dart-js/dart-js-library){._links-link}

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
greater than [length](length).

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3, 4];
const index = 2;
numbers.insert(index, 10);
print(numbers); // [1, 2, 10, 3, 4]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external void insert(int index, E element);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js/JsArray/insert.html>
:::
