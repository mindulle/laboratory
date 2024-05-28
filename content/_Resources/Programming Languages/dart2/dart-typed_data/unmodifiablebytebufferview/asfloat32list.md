[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

asFloat32List method
====================

::: {.section .multi-line-signature}
[Float32List](../float32list-class) asFloat32List(

1.  \[[int](../../dart-core/int-class) offsetInBytes = 0,
2.  [int](../../dart-core/int-class)? length\]

)

::: {.features}
override
:::
:::

Creates a [Float32List](../float32list-class) *view* of a region of this
byte buffer.

The view is backed by the bytes of this byte buffer. Any changes made to
the `Float32List` will also change the buffer, and vice versa.

The viewed region start at `offsetInBytes`, which must be 32-bit
aligned, and contains `length` 32-bit integers. If `length` is omitted,
the range extends as far towards the end of the buffer as possible - if
[lengthInBytes](lengthinbytes) is not divisible by four, the last bytes
can\'t be part of the view.

The start index and length must describe a valid 32-bit aligned range of
the buffer:

-   `offsetInBytes` must not be negative,
-   `offsetInBytes` must be divisible by four,
-   `length` must not be negative, and
-   `offsetInBytes + length * 4` must not be greater than
    [lengthInBytes](lengthinbytes).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Float32List asFloat32List([int offsetInBytes = 0, int? length]) =>
    new UnmodifiableFloat32ListView(
        _data.asFloat32List(offsetInBytes, length));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableByteBufferView/asFloat32List.html>
:::
