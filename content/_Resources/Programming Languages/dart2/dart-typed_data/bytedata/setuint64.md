[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

setUint64 method
================

::: {.section .multi-line-signature}
void setUint64(

1.  [int](../../dart-core/int-class) byteOffset,
2.  [int](../../dart-core/int-class) value,
3.  \[[Endian](../endian-class) endian = Endian.big\]

)
:::

Sets the eight bytes starting at the specified `byteOffset` in this
object to the unsigned binary representation of the specified `value`,
which must fit in eight bytes.

In other words, `value` must be between 0 and 2^64^ - 1, inclusive.

The `byteOffset` must be non-negative, and `byteOffset + 8` must be less
than or equal to the length of this object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setUint64(int byteOffset, int value, [Endian endian = Endian.big]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/ByteData/setUint64.html>
:::
