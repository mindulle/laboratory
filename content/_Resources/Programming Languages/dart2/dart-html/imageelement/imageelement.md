[dart:html](../../dart-html/dart-html-library){._links-link}

ImageElement constructor
========================

::: {.section .multi-line-signature}
ImageElement(

1.  {[String](../../dart-core/string-class)? src,
2.  [int](../../dart-core/int-class)? width,
3.  [int](../../dart-core/int-class)? height}

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory ImageElement({String? src, int? width, int? height}) {
  ImageElement e = JS<ImageElement>(
      'returns:ImageElement;creates:ImageElement;new:true',
      '#.createElement(#)',
      document,
      "img");
  if (src != null) e.src = src;
  if (width != null) e.width = width;
  if (height != null) e.height = height;
  return e;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImageElement/ImageElement.html>
:::
