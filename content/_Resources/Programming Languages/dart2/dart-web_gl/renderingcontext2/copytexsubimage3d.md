[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

copyTexSubImage3D method
========================

::: {.section .multi-line-signature}
void copyTexSubImage3D(

1.  [int](../../dart-core/int-class) target,
2.  [int](../../dart-core/int-class) level,
3.  [int](../../dart-core/int-class) xoffset,
4.  [int](../../dart-core/int-class) yoffset,
5.  [int](../../dart-core/int-class) zoffset,
6.  [int](../../dart-core/int-class) x,
7.  [int](../../dart-core/int-class) y,
8.  [int](../../dart-core/int-class) width,
9.  [int](../../dart-core/int-class) height

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void copyTexSubImage3D(int target, int level, int xoffset, int yoffset,
    int zoffset, int x, int y, int width, int height) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2/copyTexSubImage3D.html>
:::
