[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

getInt8 method
==============

::: {.section .multi-line-signature}
[int](../../dart-core/int-class) getInt8(

1.  [int](../../dart-core/int-class) byteOffset

)
:::

Returns the (possibly negative) integer represented by the byte at the
specified `byteOffset` in this object, in two\'s complement binary
representation.

The return value will be between -128 and 127, inclusive.

The `byteOffset` must be non-negative, and less than the length of this
object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
int getInt8(int byteOffset);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/ByteData/getInt8.html>
:::
