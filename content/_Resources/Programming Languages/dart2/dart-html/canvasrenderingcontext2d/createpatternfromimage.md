[dart:html](../../dart-html/dart-html-library){._links-link}

createPatternFromImage method
=============================

::: {.section .multi-line-signature}
[CanvasPattern](../canvaspattern-class) createPatternFromImage(

1.  [ImageElement](../imageelement-class) image,
2.  [String](../../dart-core/string-class) repetitionType

)
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
CanvasPattern createPatternFromImage(
        ImageElement image, String repetitionType) =>
    JS('CanvasPattern', '#.createPattern(#, #)', this, image, repetitionType);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasRenderingContext2D/createPatternFromImage.html>
:::
