[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

setFloat64 method
=================

::: {.section .multi-line-signature}
void setFloat64(

1.  [int](../../dart-core/int-class) byteOffset,
2.  [double](../../dart-core/double-class) value,
3.  \[[Endian](../endian-class) endian = Endian.big\]

)
:::

Sets the eight bytes starting at the specified `byteOffset` in this
object to the IEEE 754 double-precision binary floating-point (binary64)
representation of the specified `value`.

The `byteOffset` must be non-negative, and `byteOffset + 8` must be less
than or equal to the length of this object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setFloat64(int byteOffset, double value, [Endian endian = Endian.big]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/ByteData/setFloat64.html>
:::
