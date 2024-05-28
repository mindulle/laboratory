[dart:math](../../dart-math/dart-math-library){._links-link}

width property
==============

::: {#getter .section .multi-line-signature}
T width
:::

The width of the rectangle.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
T get width => _width;
```

::: {#setter .section .multi-line-signature}
void width=(T width)
:::

Sets the width of the rectangle.

The width must be non-negative. If a negative width is supplied, it is
clamped to zero.

Setting the value will change the right edge of the rectangle, but will
not change [left](left).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set width(T width) {
  if (width < 0) width = _clampToZero<T>(width);
  _width = width;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/MutableRectangle/width.html>
:::
