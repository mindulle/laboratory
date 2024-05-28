[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

getUint8 method
===============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) getUint8(

1.  [int](../../dart-core/int-class) byteOffset

)
:::

Returns the positive integer represented by the byte at the specified
`byteOffset` in this object, in unsigned binary form.

The return value will be between 0 and 255, inclusive.

The `byteOffset` must be non-negative, and less than the length of this
object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int getUint8(int byteOffset);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/ByteData/getUint8.html>
:::
