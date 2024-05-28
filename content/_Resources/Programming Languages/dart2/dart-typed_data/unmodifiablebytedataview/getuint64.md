[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

getUint64 method
================

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) getUint64(

1.  [int](../../dart-core/int-class) byteOffset,
2.  \[[Endian](../endian-class) endian = Endian.big\]

)

::: {.features}
override
:::
:::

Returns the positive integer represented by the eight bytes starting at
the specified `byteOffset` in this object, in unsigned binary form.

The return value will be between 0 and 2^64^ - 1, inclusive.

The `byteOffset` must be non-negative, and `byteOffset + 8` must be less
than or equal to the length of this object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int getUint64(int byteOffset, [Endian endian = Endian.big]) =>
    _data.getUint64(byteOffset, endian);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/UnmodifiableByteDataView/getUint64.html>
:::
