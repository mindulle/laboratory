[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

getInt64 method
===============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) getInt64(

1.  [int](../../dart-core/int-class) byteOffset,
2.  \[[Endian](../endian-class) endian = Endian.big\]

)
:::

Returns the (possibly negative) integer represented by the eight bytes
at the specified `byteOffset` in this object, in two\'s complement
binary form.

The return value will be between -2^63^ and 2^63^ - 1, inclusive.

The `byteOffset` must be non-negative, and `byteOffset + 8` must be less
than or equal to the length of this object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int getInt64(int byteOffset, [Endian endian = Endian.big]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/ByteData/getInt64.html>
:::
