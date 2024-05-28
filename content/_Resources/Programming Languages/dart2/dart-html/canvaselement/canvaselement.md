[dart:html](../../dart-html/dart-html-library){._links-link}

CanvasElement constructor
=========================

::: {.section .multi-line-signature}
CanvasElement(

1.  {[int](../../dart-core/int-class)? width,
2.  [int](../../dart-core/int-class)? height}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory CanvasElement({int? width, int? height}) {
  CanvasElement e = JS<CanvasElement>(
      'returns:CanvasElement;creates:CanvasElement;new:true',
      '#.createElement(#)',
      document,
      "canvas");
  if (width != null) e.width = width;
  if (height != null) e.height = height;
  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasElement/CanvasElement.html>
:::
