[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

asInt32x4List method
====================

::: {.section .multi-line-signature}
[Int32x4List](../int32x4list-class) asInt32x4List(

1.  \[[int](../../dart-core/int-class) offsetInBytes = 0,
2.  [int](../../dart-core/int-class)? length\]

)
:::

Creates a [Int32x4List](../int32x4list-class) *view* of a region of this
byte buffer.

The view is backed by the bytes of this byte buffer. Any changes made to
the `Int32x4List` will also change the buffer, and vice versa.

The viewed region start at `offsetInBytes`, which must be 128-bit
aligned, and contains `length` 128-bit integers. If `length` is omitted,
the range extends as far towards the end of the buffer as possible - if
[lengthInBytes](lengthinbytes) is not divisible by 16, the last bytes
can\'t be part of the view.

The start index and length must describe a valid 128-bit aligned range
of the buffer:

-   `offsetInBytes` must not be negative,
-   `offsetInBytes` must be divisible by sixteen,
-   `length` must not be negative, and
-   `offsetInBytes + length * 16` must not be greater than
    [lengthInBytes](lengthinbytes).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Int32x4List asInt32x4List([int offsetInBytes = 0, int? length]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/ByteBuffer/asInt32x4List.html>
:::
