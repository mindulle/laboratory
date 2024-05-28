[dart:html](../dart-html/dart-html-library){._links-link}

CssRect class
=============

A class for representing CSS dimensions.

In contrast to the more general purpose
[Rectangle](../dart-math/rectangle-class) class, this class\'s values
are mutable, so one can change the height of an element
programmatically.

*Important* *note*: use of these methods will perform CSS calculations
that can trigger a browser reflow. Therefore, use of these properties
*during* an animation frame is discouraged. See also: [Browser
Reflow](https://developers.google.com/speed/articles/reflow)

Implemented types

:   -   [Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

Constructors
------------

[CssRect](cssrect/cssrect)([Element](element-class) \_element)

Properties {#instance-properties}
----------

[bottom](cssrect/bottom) → [num](../dart-core/num-class)

::: {.features}
read-only
:::

The y-coordinate of the bottom edge.

[bottomLeft](cssrect/bottomleft) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[bottomRight](cssrect/bottomright) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[hashCode](cssrect/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

The hash code for this object.

[height](cssrect/height) ↔ [num](../dart-core/num-class)

::: {.features}
read / write, override-getter
:::

The height of this rectangle.

[left](cssrect/left) → [num](../dart-core/num-class)

::: {.features}
read-only, override
:::

The x-coordinate of the left edge.

[right](cssrect/right) → [num](../dart-core/num-class)

::: {.features}
read-only
:::

The x-coordinate of the right edge.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[top](cssrect/top) → [num](../dart-core/num-class)

::: {.features}
read-only, override
:::

The y-coordinate of the top edge.

[topLeft](cssrect/topleft) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[topRight](cssrect/topright) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[width](cssrect/width) ↔ [num](../dart-core/num-class)

::: {.features}
read / write, override-getter
:::

The width of this rectangle.

Methods {#instance-methods}
-------

[boundingBox](cssrect/boundingbox)([Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>
other) →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

Returns a new rectangle which completely contains `this` and `other`.

[containsPoint](cssrect/containspoint)([Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>
another) → [bool](../dart-core/bool-class)

Tests whether `another` is inside or along the edges of `this`.

[containsRectangle](cssrect/containsrectangle)([Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>
another) → [bool](../dart-core/bool-class)

Tests whether `this` entirely contains `another`.

[intersection](cssrect/intersection)([Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>
other) →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>?

Computes the intersection of `this` and `other`.

[intersects](cssrect/intersects)([Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>
other) → [bool](../dart-core/bool-class)

Returns true if `this` intersects `other`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](cssrect/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

A string representation of this object.

Operators
---------

[operator
==](cssrect/operator_equals)([Object](../dart-core/object-class) other)
→ [bool](../dart-core/bool-class)

::: {.features}
override
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/CssRect-class.html>
:::
