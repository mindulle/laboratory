[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

Uint8ClampedList.fromList constructor
=====================================

::: {.section .multi-line-signature}
Uint8ClampedList.fromList(

1.  [List](../../dart-core/list-class)\<[int](../../dart-core/int-class)\>
    elements

)
:::

Creates a [Uint8ClampedList](../uint8clampedlist-class) of the same size
as the `elements` list and copies over the values clamping when needed.

Values are clamped to fit in the list when they are copied, the same way
storing values clamps them.

The list is backed by a [ByteBuffer](../bytebuffer-class) containing
precisely `elements.length` bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Uint8ClampedList.fromList(List<int> elements);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Uint8ClampedList/Uint8ClampedList.fromList.html>
:::
