[dart:math](../../dart-math/dart-math-library){._links-link}

Rectangle\<T extends num\> constructor
======================================

::: {.section .multi-line-signature}
const Rectangle\<T extends num\>(

1.  T left,
2.  T top,
3.  T width,
4.  T height

)
:::

Create a rectangle spanned by `(left, top)` and
`(left+width, top+height)`.

The rectangle contains the points with x-coordinate between `left` and
`left + width`, and with y-coordinate between `top` and `top + height`,
both inclusive.

The `width` and `height` should be non-negative. If `width` or `height`
are negative, they are clamped to zero.

If `width` and `height` are zero, the \"rectangle\" comprises only the
single point `(left, top)`.

Example:

``` {.language-dart data-language="dart"}
var rectangle = const Rectangle(20, 50, 300, 600);
print(rectangle.left); // 20
print(rectangle.top); // 50
print(rectangle.right); // 320
print(rectangle.bottom); // 650
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
const Rectangle(this.left, this.top, T width, T height)
    : width = (width < 0)
          ? (width == double.negativeInfinity ? 0.0 : (-width * 0)) as dynamic
          : (width + 0 as dynamic), // Inline _clampToZero<num>.
      height = (height < 0)
          ? (height == double.negativeInfinity ? 0.0 : (-height * 0))
              as dynamic
          : (height + 0 as dynamic);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Rectangle/Rectangle.html>
:::
