[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

texSubImage2D method
====================

::: {.section .multi-line-signature}
void texSubImage2D(

1.  [int](../../dart-core/int-class) target,
2.  [int](../../dart-core/int-class) level,
3.  [int](../../dart-core/int-class) xoffset,
4.  [int](../../dart-core/int-class) yoffset,
5.  [int](../../dart-core/int-class) format\_OR\_width,
6.  [int](../../dart-core/int-class) height\_OR\_type,
7.  dynamic
    bitmap\_OR\_canvas\_OR\_format\_OR\_image\_OR\_pixels\_OR\_video,
8.  \[[int](../../dart-core/int-class)? type,
9.  [TypedData](../../dart-typed_data/typeddata-class)? pixels\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void texSubImage2D(
    int target,
    int level,
    int xoffset,
    int yoffset,
    int format_OR_width,
    int height_OR_type,
    bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video,
    [int? type,
    TypedData? pixels]) {
  if (type != null &&
      (bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video is int)) {
    _texSubImage2D_1(
        target,
        level,
        xoffset,
        yoffset,
        format_OR_width,
        height_OR_type,
        bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video,
        type,
        pixels);
    return;
  }
  if ((bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video is ImageData) &&
      type == null &&
      pixels == null) {
    var pixels_1 = convertDartToNative_ImageData(
        bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video);
    _texSubImage2D_2(target, level, xoffset, yoffset, format_OR_width,
        height_OR_type, pixels_1);
    return;
  }
  if ((bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video
          is ImageElement) &&
      type == null &&
      pixels == null) {
    _texSubImage2D_3(
        target,
        level,
        xoffset,
        yoffset,
        format_OR_width,
        height_OR_type,
        bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video);
    return;
  }
  if ((bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video
          is CanvasElement) &&
      type == null &&
      pixels == null) {
    _texSubImage2D_4(
        target,
        level,
        xoffset,
        yoffset,
        format_OR_width,
        height_OR_type,
        bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video);
    return;
  }
  if ((bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video
          is VideoElement) &&
      type == null &&
      pixels == null) {
    _texSubImage2D_5(
        target,
        level,
        xoffset,
        yoffset,
        format_OR_width,
        height_OR_type,
        bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video);
    return;
  }
  if ((bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video
          is ImageBitmap) &&
      type == null &&
      pixels == null) {
    _texSubImage2D_6(
        target,
        level,
        xoffset,
        yoffset,
        format_OR_width,
        height_OR_type,
        bitmap_OR_canvas_OR_format_OR_image_OR_pixels_OR_video);
    return;
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext/texSubImage2D.html>
:::
