[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

asUint8ClampedList method
=========================

::: {.section .multi-line-signature}
[Uint8ClampedList](../uint8clampedlist-class) asUint8ClampedList(

1.  \[[int](../../dart-core/int-class) offsetInBytes = 0,
2.  [int](../../dart-core/int-class)? length\]

)

::: {.features}
override
:::
:::

Creates a [Uint8ClampedList](../uint8clampedlist-class) *view* of a
region of this byte buffer.

The view is backed by the bytes of this byte buffer. Any changes made to
the `Uint8ClampedList` will also change the buffer, and vice versa.

The viewed region start at `offsetInBytes` and contains `length` bytes.
If `length` is omitted, the range extends to the end of the buffer.

The start index and length must describe a valid range of the buffer:

-   `offsetInBytes` must not be negative,
-   `length` must not be negative, and
-   `offsetInBytes + length` must not be greater than
    [lengthInBytes](lengthinbytes).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Uint8ClampedList asUint8ClampedList([int offsetInBytes = 0, int? length]) =>
    new UnmodifiableUint8ClampedListView(
        _data.asUint8ClampedList(offsetInBytes, length));
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableByteBufferView/asUint8ClampedList.html>
:::
