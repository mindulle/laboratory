[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

asUint16List method
===================

::: {.section .multi-line-signature}
[Uint16List](../uint16list-class) asUint16List(

1.  \[[int](../../dart-core/int-class) offsetInBytes = 0,
2.  [int](../../dart-core/int-class)? length\]

)

::: {.features}
override
:::
:::

Creates a [Uint16List](../uint16list-class) *view* of a region of this
byte buffer.

The view is backed by the bytes of this byte buffer. Any changes made to
the `Uint16List` will also change the buffer, and vice versa.

The viewed region start at `offsetInBytes`, which must be 16-bit
aligned, and contains `length` 16-bit integers with the same endianness
as the host ([Endian.host](../endian/host)). If `length` is omitted, the
range extends as far towards the end of the buffer as possible - if
[lengthInBytes](lengthinbytes) is not even, the last byte can\'t be part
of the view.

The start index and length must describe a valid 16-bit aligned range of
the buffer:

-   `offsetInBytes` must not be negative,
-   `offsetInBytes` must be divisible by two,
-   `length` must not be negative, and
-   `offsetInBytes + length * 2` must not be greater than
    [lengthInBytes](lengthinbytes).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint16List asUint16List([int offsetInBytes = 0, int? length]) =>
    new UnmodifiableUint16ListView(_data.asUint16List(offsetInBytes, length));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableByteBufferView/asUint16List.html>
:::
