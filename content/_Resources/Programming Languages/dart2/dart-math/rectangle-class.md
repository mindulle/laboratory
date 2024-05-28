[dart:math](../dart-math/dart-math-library){._links-link}

Rectangle\<T extends num\> class
================================

A class for representing two-dimensional rectangles whose properties are
immutable.

Implementers

:   -   [CssRect](../dart-html/cssrect-class)
    -   [DomRectReadOnly](../dart-html/domrectreadonly-class)
    -   [MutableRectangle](mutablerectangle-class)

Constructors
------------

[Rectangle](rectangle/rectangle)(T left, T top, T width, T height)

::: {.constructor-modifier .features}
const
:::

Create a rectangle spanned by `(left, top)` and
`(left+width, top+height)`.

[Rectangle.fromPoints](rectangle/rectangle.frompoints)([Point](point-class)\<T\>
a, [Point](point-class)\<T\> b)

::: {.constructor-modifier .features}
factory
:::

Create a rectangle spanned by the points `a` and `b`;

Properties {#instance-properties}
----------

[bottom](rectangle/bottom) → T

::: {.features}
read-only, inherited
:::

The y-coordinate of the bottom edge.

[bottomLeft](rectangle/bottomleft) → [Point](point-class)\<T\>

::: {.features}
read-only, inherited
:::

[bottomRight](rectangle/bottomright) → [Point](point-class)\<T\>

::: {.features}
read-only, inherited
:::

[hashCode](rectangle/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[height](rectangle/height) → T

::: {.features}
final
:::

The height of the rectangle.

[left](rectangle/left) → T

::: {.features}
final
:::

The x-coordinate of the left edge.

[right](rectangle/right) → T

::: {.features}
read-only, inherited
:::

The x-coordinate of the right edge.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[top](rectangle/top) → T

::: {.features}
final
:::

The y-coordinate of the top edge.

[topLeft](rectangle/topleft) → [Point](point-class)\<T\>

::: {.features}
read-only, inherited
:::

[topRight](rectangle/topright) → [Point](point-class)\<T\>

::: {.features}
read-only, inherited
:::

[width](rectangle/width) → T

::: {.features}
final
:::

The width of the rectangle.

Methods {#instance-methods}
-------

[boundingBox](rectangle/boundingbox)([Rectangle](rectangle-class)\<T\>
other) → [Rectangle](rectangle-class)\<T\>

::: {.features}
inherited
:::

Returns a new rectangle which completely contains `this` and `other`.

[containsPoint](rectangle/containspoint)([Point](point-class)\<[num](../dart-core/num-class)\>
another) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Tests whether `another` is inside or along the edges of `this`.

[containsRectangle](rectangle/containsrectangle)([Rectangle](rectangle-class)\<[num](../dart-core/num-class)\>
another) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Tests whether `this` entirely contains `another`.

[intersection](rectangle/intersection)([Rectangle](rectangle-class)\<T\>
other) → [Rectangle](rectangle-class)\<T\>?

::: {.features}
inherited
:::

Computes the intersection of `this` and `other`.

[intersects](rectangle/intersects)([Rectangle](rectangle-class)\<[num](../dart-core/num-class)\>
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

Returns true if `this` intersects `other`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](rectangle/tostring)() → [String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](rectangle/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Rectangle-class.html>
:::
