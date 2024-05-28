[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

texImage2DUntyped method
========================

::: {.section .multi-line-signature}
<div>

1.  @[Deprecated](../../dart-core/deprecated-class)(\"Use texImage2D\")

</div>

void texImage2DUntyped(

1.  [int](../../dart-core/int-class) targetTexture,
2.  [int](../../dart-core/int-class) levelOfDetail,
3.  [int](../../dart-core/int-class) internalFormat,
4.  [int](../../dart-core/int-class) format,
5.  [int](../../dart-core/int-class) type,
6.  dynamic data

)

::: {.features}
@[Deprecated](../../dart-core/deprecated-class)(\"Use texImage2D\")
:::
:::

Sets the currently bound texture to `data`.

`data` can be either an
[ImageElement](../../dart-html/imageelement-class), a
[CanvasElement](../../dart-html/canvaselement-class), a
[VideoElement](../../dart-html/videoelement-class),
[TypedData](../../dart-typed_data/typeddata-class) or an
[ImageData](../../dart-html/imagedata-class) object.

This is deprecated in favor of [texImage2D](teximage2d).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Deprecated("Use texImage2D")
void texImage2DUntyped(int targetTexture, int levelOfDetail,
    int internalFormat, int format, int type, data) {
  texImage2D(
      targetTexture, levelOfDetail, internalFormat, format, type, data);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/texImage2DUntyped.html>
:::
