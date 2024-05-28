[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

asUint64List method
===================

::: {.section .multi-line-signature}
[Uint64List](../uint64list-class) asUint64List(

1.  \[[int](../../dart-core/int-class) offsetInBytes = 0,
2.  [int](../../dart-core/int-class)? length\]

)
:::

Creates a [Uint64List](../uint64list-class) *view* of a region of this
byte buffer.

The view is backed by the bytes of this byte buffer. Any changes made to
the `Uint64List` will also change the buffer, and vice versa.

The viewed region start at `offsetInBytes`, which must be 64-bit
aligned, and contains `length` 64-bit integers with the same endianness
as the host ([Endian.host](../endian/host)). If `length` is omitted, the
range extends as far towards the end of the buffer as possible - if
[lengthInBytes](lengthinbytes) is not divisible by eight, the last bytes
can\'t be part of the view.

The start index and length must describe a valid 64-bit aligned range of
the buffer:

-   `offsetInBytes` must not be negative,
-   `offsetInBytes` must be divisible by eight,
-   `length` must not be negative, and
-   `offsetInBytes + length * 8` must not be greater than
    [lengthInBytes](lengthinbytes).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint64List asUint64List([int offsetInBytes = 0, int? length]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/ByteBuffer/asUint64List.html>
:::
