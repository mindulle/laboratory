[dart:html](../../dart-html/dart-html-library){._links-link}

containsRectangle method
========================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) containsRectangle(

1.  [Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>
    another

)
:::

Tests whether `this` entirely contains `another`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool containsRectangle(Rectangle<num> another) {
  return left <= another.left &&
      left + width >= another.left + another.width &&
      top <= another.top &&
      top + height >= another.top + another.height;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssRect/containsRectangle.html>
:::
