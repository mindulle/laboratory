[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

texSubImage2DTyped method
=========================

::: {.section .multi-line-signature}
<div>

1.  @[Deprecated](../../dart-core/deprecated-class)(\"Use
    texSubImage2D\")

</div>

void texSubImage2DTyped(

1.  [int](../../dart-core/int-class) targetTexture,
2.  [int](../../dart-core/int-class) levelOfDetail,
3.  [int](../../dart-core/int-class) xOffset,
4.  [int](../../dart-core/int-class) yOffset,
5.  [int](../../dart-core/int-class) width,
6.  [int](../../dart-core/int-class) height,
7.  [int](../../dart-core/int-class) border,
8.  [int](../../dart-core/int-class) format,
9.  [int](../../dart-core/int-class) type,
10. [TypedData](../../dart-typed_data/typeddata-class) data

)

::: {.features}
@[Deprecated](../../dart-core/deprecated-class)(\"Use texSubImage2D\")
:::
:::

Updates a sub-rectangle of the currently bound texture to `data`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Deprecated("Use texSubImage2D")
void texSubImage2DTyped(
    int targetTexture,
    int levelOfDetail,
    int xOffset,
    int yOffset,
    int width,
    int height,
    int border,
    int format,
    int type,
    TypedData data) {
  texSubImage2D(targetTexture, levelOfDetail, xOffset, yOffset, width, height,
      format, type, data);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/texSubImage2DTyped.html>
:::
