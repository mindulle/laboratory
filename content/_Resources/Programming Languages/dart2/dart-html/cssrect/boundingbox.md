[dart:html](../../dart-html/dart-html-library){._links-link}

boundingBox method
==================

::: {.section .multi-line-signature}
[Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>
boundingBox(

1.  [Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>
    other

)
:::

Returns a new rectangle which completely contains `this` and `other`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Rectangle<num> boundingBox(Rectangle<num> other) {
  var right = max(this.left + this.width, other.left + other.width);
  var bottom = max(this.top + this.height, other.top + other.height);

  var left = min(this.left, other.left);
  var top = min(this.top, other.top);

  return new Rectangle<num>(left, top, right - left, bottom - top);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssRect/boundingBox.html>
:::
