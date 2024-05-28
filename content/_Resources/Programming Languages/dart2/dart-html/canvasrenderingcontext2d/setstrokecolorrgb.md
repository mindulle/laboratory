[dart:html](../../dart-html/dart-html-library){._links-link}

setStrokeColorRgb method
========================

::: {.section .multi-line-signature}
void setStrokeColorRgb(

1.  [int](../../dart-core/int-class) r,
2.  [int](../../dart-core/int-class) g,
3.  [int](../../dart-core/int-class) b,
4.  \[[num](../../dart-core/num-class) a = 1\]

)
:::

Sets the color used for stroking shapes. `r`, `g`, `b` are 0-255, `a` is
0-1.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setStrokeColorRgb(int r, int g, int b, [num a = 1]) {
  this.strokeStyle = 'rgba($r, $g, $b, $a)';
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/setStrokeColorRgb.html>
:::
