dart:math library
=================

Mathematical constants and functions, plus a random number generator.

To use this library in your code:

``` {.language-dart data-language="dart"}
import 'dart:math';
```

Random
------

[Random](random-class) is a generator of
[bool](../dart-core/bool-class), [int](../dart-core/int-class) or
[double](../dart-core/double-class) values.

``` {.language-dart data-language="dart"}
var intValue = Random().nextInt(10); // Value is >= 0 and < 10.
var doubleValue = Random().nextDouble(); // Value is >= 0.0 and < 1.0.
var boolValue = Random().nextBool(); // true or false, with equal chance.
```

Point
-----

[Point](point-class) is a utility class for representing two-dimensional
positions.

``` {.language-dart data-language="dart"}
var leftTop = const Point(0, 0);
var rightBottom = const Point(200, 400);
```

Rectangle
---------

[Rectangle](rectangle-class) is a class for representing two-dimensional
axis-aligned rectangles whose properties are immutable.

Create a rectangle spanned by the points.

``` {.language-dart data-language="dart"}
var leftTop = const Point(20, 50);
var rightBottom = const Point(300, 600);
var rectangle = Rectangle.fromPoints(leftTop, rightBottom);
print(rectangle.left); // 20
print(rectangle.top); // 50
print(rectangle.right); // 300
print(rectangle.bottom); // 600
```

Create a rectangle spanned by `(left, top)` and
`(left+width, top+height)`.

``` {.language-dart data-language="dart"}
var rectangle = const Rectangle(20, 50, 300, 600);
print(rectangle.left); // 20
print(rectangle.top); // 50
print(rectangle.right); // 320
print(rectangle.bottom); // 650
```

MutableRectangle
----------------

[MutableRectangle](mutablerectangle-class) is a class for representing
two-dimensional axis-aligned rectangles with mutable properties.

Create a mutable rectangle spanned by `(left, top)` and
`(left+width, top+height)`.

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

Classes
-------

[MutableRectangle](mutablerectangle-class)\<T extends [num](../dart-core/num-class)\>
:   A class for representing two-dimensional axis-aligned rectangles
    with mutable properties.

[Point](point-class)\<T extends [num](../dart-core/num-class)\>
:   A utility class for representing two-dimensional positions.

[Random](random-class)
:   A generator of random bool, int, or double values.

[Rectangle](rectangle-class)\<T extends [num](../dart-core/num-class)\>
:   A class for representing two-dimensional rectangles whose properties
    are immutable.

Constants
---------

[e](e-constant) → const [double](../dart-core/double-class)
:   Base of the natural logarithms.
    <div>

    `2.718281828459045`

    </div>

[ln10](ln10-constant) → const [double](../dart-core/double-class)
:   Natural logarithm of 10.
    <div>

    `2.302585092994046`

    </div>

[ln2](ln2-constant) → const [double](../dart-core/double-class)
:   Natural logarithm of 2.
    <div>

    `0.6931471805599453`

    </div>

[log10e](log10e-constant) → const [double](../dart-core/double-class)
:   Base-10 logarithm of [e](e-constant).
    <div>

    `0.4342944819032518`

    </div>

[log2e](log2e-constant) → const [double](../dart-core/double-class)
:   Base-2 logarithm of [e](e-constant).
    <div>

    `1.4426950408889634`

    </div>

[pi](pi-constant) → const [double](../dart-core/double-class)
:   The PI constant.
    <div>

    `3.1415926535897932`

    </div>

[sqrt1\_2](sqrt1_2-constant) → const [double](../dart-core/double-class)
:   Square root of 1/2.
    <div>

    `0.7071067811865476`

    </div>

[sqrt2](sqrt2-constant) → const [double](../dart-core/double-class)
:   Square root of 2.
    <div>

    `1.4142135623730951`

    </div>

Functions
---------

[acos](acos)([num](../dart-core/num-class) x) → [double](../dart-core/double-class)
:   Converts `x` to a [double](../dart-core/double-class) and returns
    its arc cosine in radians.

[asin](asin)([num](../dart-core/num-class) x) → [double](../dart-core/double-class)
:   Converts `x` to a [double](../dart-core/double-class) and returns
    its arc sine in radians.

[atan](atan)([num](../dart-core/num-class) x) → [double](../dart-core/double-class)
:   Converts `x` to a [double](../dart-core/double-class) and returns
    its arc tangent in radians.

[atan2](atan2)([num](../dart-core/num-class) a, [num](../dart-core/num-class) b) → [double](../dart-core/double-class)
:   A variant of [atan](atan).

[cos](cos)([num](../dart-core/num-class) radians) → [double](../dart-core/double-class)
:   Converts `radians` to a [double](../dart-core/double-class) and
    returns the cosine of the value.

[exp](exp)([num](../dart-core/num-class) x) → [double](../dart-core/double-class)
:   Converts `x` to a [double](../dart-core/double-class) and returns
    the natural exponent, [e](e-constant), to the power `x`.

[log](log)([num](../dart-core/num-class) x) → [double](../dart-core/double-class)
:   Converts `x` to a [double](../dart-core/double-class) and returns
    the natural logarithm of the value.

[max](max)\<T extends [num](../dart-core/num-class)\>(T a, T b) → T
:   Returns the larger of two numbers.

[min](min)\<T extends [num](../dart-core/num-class)\>(T a, T b) → T
:   Returns the lesser of two numbers.

[pow](pow)([num](../dart-core/num-class) x, [num](../dart-core/num-class) exponent) → [num](../dart-core/num-class)
:   Returns `x` to the power of `exponent`.

[sin](sin)([num](../dart-core/num-class) radians) → [double](../dart-core/double-class)
:   Converts `radians` to a [double](../dart-core/double-class) and
    returns the sine of the value.

[sqrt](sqrt)([num](../dart-core/num-class) x) → [double](../dart-core/double-class)
:   Converts `x` to a [double](../dart-core/double-class) and returns
    the positive square root of the value.

[tan](tan)([num](../dart-core/num-class) radians) → [double](../dart-core/double-class)
:   Converts `radians` to a [double](../dart-core/double-class) and
    returns the tangent of the value.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/dart-math-library.html>
:::
