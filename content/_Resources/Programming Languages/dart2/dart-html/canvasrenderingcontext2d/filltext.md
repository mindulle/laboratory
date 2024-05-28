[dart:html](../../dart-html/dart-html-library){._links-link}

fillText method
===============

::: {.section .multi-line-signature}
void fillText(

1.  [String](../../dart-core/string-class) text,
2.  [num](../../dart-core/num-class) x,
3.  [num](../../dart-core/num-class) y,
4.  \[[num](../../dart-core/num-class)? maxWidth\]

)
:::

Draws text to the canvas.

The text is drawn starting at coordinates (`x`, `y`). If `maxWidth` is
provided and the `text` is computed to be wider than `maxWidth`, then
the drawn text is scaled down horizontally to fit.

The text uses the current [CanvasRenderingContext2D.font](font) property
for font options, such as typeface and size, and the current
[CanvasRenderingContext2D.fillStyle](fillstyle) for style options such
as color. The current [CanvasRenderingContext2D.textAlign](textalign)
and [CanvasRenderingContext2D.textBaseline](textbaseline) properties are
also applied to the drawn text.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void fillText(String text, num x, num y, [num? maxWidth]) {
  if (maxWidth != null) {
    JS('void', '#.fillText(#, #, #, #)', this, text, x, y, maxWidth);
  } else {
    JS('void', '#.fillText(#, #, #)', this, text, x, y);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/fillText.html>
:::
