[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

compressedTexImage3D method
===========================

::: {.section .multi-line-signature}
void compressedTexImage3D(

1.  [int](../../dart-core/int-class) target,
2.  [int](../../dart-core/int-class) level,
3.  [int](../../dart-core/int-class) internalformat,
4.  [int](../../dart-core/int-class) width,
5.  [int](../../dart-core/int-class) height,
6.  [int](../../dart-core/int-class) depth,
7.  [int](../../dart-core/int-class) border,
8.  [TypedData](../../dart-typed_data/typeddata-class) data,
9.  \[[int](../../dart-core/int-class)? srcOffset,
10. [int](../../dart-core/int-class)? srcLengthOverride\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void compressedTexImage3D(int target, int level, int internalformat,
    int width, int height, int depth, int border, TypedData data,
    [int? srcOffset, int? srcLengthOverride]) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2/compressedTexImage3D.html>
:::
