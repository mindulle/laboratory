[dart:collection](../../dart-collection/dart-collection-library){._links-link}

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
int get length => _source.length;
```

::: {#setter .section .multi-line-signature}
void length=([int](../../dart-core/int-class) newLength)

::: {.features}
inherited
:::
:::

This operation is not supported by an unmodifiable list.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set length(int newLength) {
  throw new UnsupportedError(
      "Cannot change the length of an unmodifiable list");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/UnmodifiableListView/length.html>
:::
