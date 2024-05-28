[dart:math](../../dart-math/dart-math-library){._links-link}

height property
===============

::: {#getter .section .multi-line-signature}
T height
:::

The height of the rectangle.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
T get height => _height;
```

::: {#setter .section .multi-line-signature}
void height=(T height)
:::

Sets the height of the rectangle.

The height must be non-negative. If a negative height is supplied, it is
clamped to zero.

Setting the value will change the bottom edge of the rectangle, but will
not change [top](top).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
set height(T height) {
  if (height < 0) height = _clampToZero<T>(height);
  _height = height;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/MutableRectangle/height.html>
:::
