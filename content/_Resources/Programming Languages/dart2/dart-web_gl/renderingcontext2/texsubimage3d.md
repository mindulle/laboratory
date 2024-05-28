[dart:web\_gl](../../dart-web_gl/dart-web_gl-library){._links-link}

texSubImage3D method
====================

::: {.section .multi-line-signature}
void texSubImage3D(

1.  [int](../../dart-core/int-class) target,
2.  [int](../../dart-core/int-class) level,
3.  [int](../../dart-core/int-class) xoffset,
4.  [int](../../dart-core/int-class) yoffset,
5.  [int](../../dart-core/int-class) zoffset,
6.  [int](../../dart-core/int-class) width,
7.  [int](../../dart-core/int-class) height,
8.  [int](../../dart-core/int-class) depth,
9.  [int](../../dart-core/int-class) format,
10. [int](../../dart-core/int-class) type,
11. dynamic
    bitmap\_OR\_canvas\_OR\_data\_OR\_image\_OR\_offset\_OR\_pixels\_OR\_video,
12. \[[int](../../dart-core/int-class)? srcOffset\]

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void texSubImage3D(
    int target,
    int level,
    int xoffset,
    int yoffset,
    int zoffset,
    int width,
    int height,
    int depth,
    int format,
    int type,
    bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video,
    [int? srcOffset]) {
  if ((bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video
          is int) &&
      srcOffset == null) {
    _texSubImage3D_1(
        target,
        level,
        xoffset,
        yoffset,
        zoffset,
        width,
        height,
        depth,
        format,
        type,
        bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video);
    return;
  }
  if ((bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video
          is ImageData) &&
      srcOffset == null) {
    var data_1 = convertDartToNative_ImageData(
        bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video);
    _texSubImage3D_2(target, level, xoffset, yoffset, zoffset, width, height,
        depth, format, type, data_1);
    return;
  }
  if ((bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video
          is ImageElement) &&
      srcOffset == null) {
    _texSubImage3D_3(
        target,
        level,
        xoffset,
        yoffset,
        zoffset,
        width,
        height,
        depth,
        format,
        type,
        bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video);
    return;
  }
  if ((bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video
          is CanvasElement) &&
      srcOffset == null) {
    _texSubImage3D_4(
        target,
        level,
        xoffset,
        yoffset,
        zoffset,
        width,
        height,
        depth,
        format,
        type,
        bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video);
    return;
  }
  if ((bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video
          is VideoElement) &&
      srcOffset == null) {
    _texSubImage3D_5(
        target,
        level,
        xoffset,
        yoffset,
        zoffset,
        width,
        height,
        depth,
        format,
        type,
        bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video);
    return;
  }
  if ((bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video
          is ImageBitmap) &&
      srcOffset == null) {
    _texSubImage3D_6(
        target,
        level,
        xoffset,
        yoffset,
        zoffset,
        width,
        height,
        depth,
        format,
        type,
        bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video);
    return;
  }
  if ((bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video
          is TypedData) &&
      srcOffset == null) {
    _texSubImage3D_7(
        target,
        level,
        xoffset,
        yoffset,
        zoffset,
        width,
        height,
        depth,
        format,
        type,
        bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video);
    return;
  }
  if (srcOffset != null &&
      (bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video
          is TypedData)) {
    _texSubImage3D_8(
        target,
        level,
        xoffset,
        yoffset,
        zoffset,
        width,
        height,
        depth,
        format,
        type,
        bitmap_OR_canvas_OR_data_OR_image_OR_offset_OR_pixels_OR_video,
        srcOffset);
    return;
  }
  throw new ArgumentError("Incorrect number or type of arguments");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_gl/RenderingContext2/texSubImage3D.html>
:::
