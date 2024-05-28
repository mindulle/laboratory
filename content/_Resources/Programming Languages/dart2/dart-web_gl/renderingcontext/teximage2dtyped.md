[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

texImage2DTyped method
======================

::: {.section .multi-line-signature}
<div>

1.  @[Deprecated](../../dart-core/deprecated-class)(\"Use texImage2D\")

</div>

void texImage2DTyped(

1.  [int](../../dart-core/int-class) targetTexture,
2.  [int](../../dart-core/int-class) levelOfDetail,
3.  [int](../../dart-core/int-class) internalFormat,
4.  [int](../../dart-core/int-class) width,
5.  [int](../../dart-core/int-class) height,
6.  [int](../../dart-core/int-class) border,
7.  [int](../../dart-core/int-class) format,
8.  [int](../../dart-core/int-class) type,
9.  [TypedData](../../dart-typed_data/typeddata-class) data

)

::: {.features}
@[Deprecated](../../dart-core/deprecated-class)(\"Use texImage2D\")
:::
:::

Sets the currently bound texture to `data`.

This is deprecated in favour of [texImage2D](teximage2d).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Deprecated("Use texImage2D")
void texImage2DTyped(int targetTexture, int levelOfDetail, int internalFormat,
    int width, int height, int border, int format, int type, TypedData data) {
  texImage2D(targetTexture, levelOfDetail, internalFormat, width, height,
      border, format, type, data);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/texImage2DTyped.html>
:::
