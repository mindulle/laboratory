[dart:html](../../dart-html/dart-html-library){._links-link}

intersection method
===================

::: {.section .multi-line-signature}
[Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>?
intersection(

1.  [Rectangle](../../dart-math/rectangle-class)\<[num](../../dart-core/num-class)\>
    other

)
:::

Computes the intersection of `this` and `other`.

The intersection of two axis-aligned rectangles, if any, is always
another axis-aligned rectangle.

Returns the intersection of this and `other`, or `null` if they don\'t
intersect.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Rectangle<num>? intersection(Rectangle<num> other) {
  var x0 = max(left, other.left);
  var x1 = min(left + width, other.left + other.width);

  if (x0 <= x1) {
    var y0 = max(top, other.top);
    var y1 = min(top + height, other.top + other.height);

    if (y0 <= y1) {
      return new Rectangle<num>(x0, y0, x1 - x0, y1 - y0);
    }
  }
  return null;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssRect/intersection.html>
:::
