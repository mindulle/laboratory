[dart:math](../../dart-math/dart-math-library){._links-link}

boundingBox method
==================

::: {.section .multi-line-signature}
[Rectangle](../rectangle-class)\<T\> boundingBox(

1.  [Rectangle](../rectangle-class)\<T\> other

)

::: {.features}
inherited
:::
:::

Returns a new rectangle which completely contains `this` and `other`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Rectangle<T> boundingBox(Rectangle<T> other) {
  var right = max(this.left + this.width, other.left + other.width);
  var bottom = max(this.top + this.height, other.top + other.height);

  var left = min(this.left, other.left);
  var top = min(this.top, other.top);

  return Rectangle<T>(left, top, (right - left) as T, (bottom - top) as T);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Rectangle/boundingBox.html>
:::
