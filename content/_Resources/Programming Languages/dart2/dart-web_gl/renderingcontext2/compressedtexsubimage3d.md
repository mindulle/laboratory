[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

compressedTexSubImage3D method
==============================

::: {.section .multi-line-signature}
void compressedTexSubImage3D(

1.  [int](../../dart-core/int-class) target,
2.  [int](../../dart-core/int-class) level,
3.  [int](../../dart-core/int-class) xoffset,
4.  [int](../../dart-core/int-class) yoffset,
5.  [int](../../dart-core/int-class) zoffset,
6.  [int](../../dart-core/int-class) width,
7.  [int](../../dart-core/int-class) height,
8.  [int](../../dart-core/int-class) depth,
9.  [int](../../dart-core/int-class) format,
10. [TypedData](../../dart-typed_data/typeddata-class) data,
11. \[[int](../../dart-core/int-class)? srcOffset,
12. [int](../../dart-core/int-class)? srcLengthOverride\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void compressedTexSubImage3D(int target, int level, int xoffset, int yoffset,
    int zoffset, int width, int height, int depth, int format, TypedData data,
    [int? srcOffset, int? srcLengthOverride]) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2/compressedTexSubImage3D.html>
:::
