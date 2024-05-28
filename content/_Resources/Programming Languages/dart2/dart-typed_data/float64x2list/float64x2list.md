[dart:typed\_data](../../dart-typed_data/dart-typed_data-library){._links-link}

Float64x2List constructor
=========================

::: {.section .multi-line-signature}
Float64x2List(

1.  [int](../../dart-core/int-class) length

)
:::

Creates a [Float64x2List](../float64x2list-class) of the specified
length (in elements), all of whose elements have all lanes set to zero.

The list is backed by a [ByteBuffer](../bytebuffer-class) containing
precisely `length` times 16 bytes.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory Float64x2List(int length);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-typed_data/Float64x2List/Float64x2List.html>
:::
