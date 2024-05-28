[dart:math](../../dart-math/dart-math-library){._links-link}

MutableRectangle\<T extends num\> constructor
=============================================

::: {.section .multi-line-signature}
MutableRectangle\<T extends num\>(

1.  T left,
2.  T top,
3.  T width,
4.  T height

)
:::

Create a mutable rectangle spanned by `(left, top)` and
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
var rectangle = MutableRectangle(20, 50, 300, 600);
print(rectangle); // Rectangle (20, 50) 300 x 600
print(rectangle.left); // 20
print(rectangle.top); // 50
print(rectangle.right); // 320
print(rectangle.bottom); // 650

// Change rectangle width and height.
rectangle.width = 200;
rectangle.height = 100;

print(rectangle); // Rectangle (20, 50) 200 x 100
print(rectangle.left); // 20
print(rectangle.top); // 50
print(rectangle.right); // 220
print(rectangle.bottom); // 150
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
MutableRectangle(this.left, this.top, T width, T height)
    : this._width =
          (width < 0) ? _clampToZero<T>(width) : (width + 0 as dynamic),
      this._height =
          (height < 0) ? _clampToZero<T>(height) : (height + 0 as dynamic);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/MutableRectangle/MutableRectangle.html>
:::
