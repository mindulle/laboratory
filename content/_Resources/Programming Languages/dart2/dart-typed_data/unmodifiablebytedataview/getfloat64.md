[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

getFloat64 method
=================

::: {.section .multi-line-signature}
[double](../../dart-core/double-class) getFloat64(

1.  [int](../../dart-core/int-class) byteOffset,
2.  \[[Endian](../endian-class) endian = Endian.big\]

)

::: {.features}
override
:::
:::

Returns the floating point number represented by the eight bytes at the
specified `byteOffset` in this object, in IEEE 754 double-precision
binary floating-point format (binary64).

The `byteOffset` must be non-negative, and `byteOffset + 8` must be less
than or equal to the length of this object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
double getFloat64(int byteOffset, [Endian endian = Endian.big]) =>
    _data.getFloat64(byteOffset, endian);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableByteDataView/getFloat64.html>
:::
