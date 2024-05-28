[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

texSubImage2DUntyped method
===========================

::: {.section .multi-line-signature}
<div>

1.  @[Deprecated](../../dart-core/deprecated-class)(\"Use
    texSubImage2D\")

</div>

void texSubImage2DUntyped(

1.  [int](../../dart-core/int-class) targetTexture,
2.  [int](../../dart-core/int-class) levelOfDetail,
3.  [int](../../dart-core/int-class) xOffset,
4.  [int](../../dart-core/int-class) yOffset,
5.  [int](../../dart-core/int-class) format,
6.  [int](../../dart-core/int-class) type,
7.  dynamic data

)

::: {.features}
@[Deprecated](../../dart-core/deprecated-class)(\"Use texSubImage2D\")
:::
:::

Updates a sub-rectangle of the currently bound texture to `data`.

`data` can be either an
[ImageElement](../../dart-html/imageelement-class), a
[CanvasElement](../../dart-html/canvaselement-class), a
[VideoElement](../../dart-html/videoelement-class),
[TypedData](../../dart-typed_data/typeddata-class) or an
[ImageData](../../dart-html/imagedata-class) object.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Deprecated("Use texSubImage2D")
void texSubImage2DUntyped(int targetTexture, int levelOfDetail, int xOffset,
    int yOffset, int format, int type, data) {
  texSubImage2D(
      targetTexture, levelOfDetail, xOffset, yOffset, format, type, data);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/texSubImage2DUntyped.html>
:::
