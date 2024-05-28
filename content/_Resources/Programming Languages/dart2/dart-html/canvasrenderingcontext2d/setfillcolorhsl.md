[dart:html](../../dart-html/dart-html-library){._links-link}

setFillColorHsl method
======================

::: {.section .multi-line-signature}
void setFillColorHsl(

1.  [int](../../dart-core/int-class) h,
2.  [num](../../dart-core/num-class) s,
3.  [num](../../dart-core/num-class) l,
4.  \[[num](../../dart-core/num-class) a = 1\]

)
:::

Sets the color used inside shapes. `h` is in degrees, 0-360. `s`, `l`
are in percent, 0-100. `a` is 0-1.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void setFillColorHsl(int h, num s, num l, [num a = 1]) {
  this.fillStyle = 'hsla($h, $s%, $l%, $a)';
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/setFillColorHsl.html>
:::
