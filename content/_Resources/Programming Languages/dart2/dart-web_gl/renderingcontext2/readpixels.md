[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

readPixels method
=================

::: {.section .multi-line-signature}
void readPixels(

1.  [int](../../dart-core/int-class) x,
2.  [int](../../dart-core/int-class) y,
3.  [int](../../dart-core/int-class) width,
4.  [int](../../dart-core/int-class) height,
5.  [int](../../dart-core/int-class) format,
6.  [int](../../dart-core/int-class) type,
7.  [TypedData](../../dart-typed_data/typeddata-class) pixels

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void readPixels(int x, int y, int width, int height, int format, int type,
    TypedData pixels) {
  _readPixels(x, y, width, height, format, type, pixels);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2/readPixels.html>
:::
