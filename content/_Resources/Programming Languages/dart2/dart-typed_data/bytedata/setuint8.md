[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

setUint8 method
===============

::: {.section .multi-line-signature}
void setUint8(

1.  [int](../../dart-core/int-class) byteOffset,
2.  [int](../../dart-core/int-class) value

)
:::

Sets the byte at the specified `byteOffset` in this object to the
unsigned binary representation of the specified `value`, which must fit
in a single byte.

In other words, `value` must be between 0 and 255, inclusive.

The `byteOffset` must be non-negative, and less than the length of this
object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setUint8(int byteOffset, int value);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/ByteData/setUint8.html>
:::
