[dart:html](../../dart-html/dart-html-library){._links-link}

addColorStop method
===================

::: {.section .multi-line-signature}
void addColorStop(

1.  [num](../../dart-core/num-class) offset,
2.  [String](../../dart-core/string-class) color

)
:::

Adds a color stop to this gradient at the offset.

The `offset` can range between 0.0 and 1.0.

See also:

-   [Multiple Color
    Stops](https://developer.mozilla.org/en-US/docs/CSS/linear-gradient#Gradient_with_multiple_color_stops)
    from MDN.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void addColorStop(num offset, String color) native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CanvasGradient/addColorStop.html>
:::
