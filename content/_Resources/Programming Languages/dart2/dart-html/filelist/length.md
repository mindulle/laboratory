[dart:html](../../dart-html/dart-html-library){._links-link}

length property
===============

::: {#getter .section .multi-line-signature}
[int](../../dart-core/int-class) length

::: {.features}
override
:::
:::

The number of objects in this list.

The valid indices for a list are `0` through `length - 1`.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
print(numbers.length); // 3
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int get length => JS("int", "#.length", this);
```

::: {#setter .section .multi-line-signature}
void length=([int](../../dart-core/int-class) value)

::: {.features}
override
:::
:::

Setting the `length` changes the number of elements in the list.

The list must be growable. If `newLength` is greater than current
length, new entries are initialized to `null`, so `newLength` must not
be greater than the current length if the element type `E` is
non-nullable.

``` {.language-dart data-language="dart"}
final maybeNumbers = <int?>[1, null, 3];
maybeNumbers.length = 5;
print(maybeNumbers); // [1, null, 3, null, null]
maybeNumbers.length = 2;
print(maybeNumbers); // [1, null]

final numbers = <int>[1, 2, 3];
numbers.length = 1;
print(numbers); // [1]
numbers.length = 5; // Throws, cannot add `null`s.
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set length(int value) {
  throw new UnsupportedError("Cannot resize immutable List.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FileList/length.html>
:::
