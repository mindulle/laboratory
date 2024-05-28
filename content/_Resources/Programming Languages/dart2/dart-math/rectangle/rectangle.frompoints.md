[dart:math](../../dart-math/dart-math-library){._links-link}

Rectangle\<T extends num\>.fromPoints constructor
=================================================

::: {.section .multi-line-signature}
Rectangle\<T extends num\>.fromPoints(

1.  [Point](../point-class)\<T\> a,
2.  [Point](../point-class)\<T\> b

)
:::

Create a rectangle spanned by the points `a` and `b`;

The rectangle contains the points with x-coordinate between `a.x` and
`b.x`, and with y-coordinate between `a.y` and `b.y`, both inclusive.

If the distance between `a.x` and `b.x` is not representable (which can
happen if one or both is a double), the actual right edge might be
slightly off from `max(a.x, b.x)`. Similar for the y-coordinates and the
bottom edge.

Example:

``` {.language-dart data-language="dart"}
var leftTop = const Point(20, 50);
var rightBottom = const Point(300, 600);

var rectangle = Rectangle.fromPoints(leftTop, rightBottom);
print(rectangle); // Rectangle (20, 50) 280 x 550
print(rectangle.left); // 20
print(rectangle.top); // 50
print(rectangle.right); // 300
print(rectangle.bottom); // 600
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Rectangle.fromPoints(Point<T> a, Point<T> b) {
  T left = min(a.x, b.x);
  T width = (max(a.x, b.x) - left) as T;
  T top = min(a.y, b.y);
  T height = (max(a.y, b.y) - top) as T;
  return Rectangle<T>(left, top, width, height);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Rectangle/Rectangle.fromPoints.html>
:::
