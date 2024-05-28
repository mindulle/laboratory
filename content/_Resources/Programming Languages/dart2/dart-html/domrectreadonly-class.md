[dart:html](../dart-html/dart-html-library){._links-link}

DomRectReadOnly class
=====================

Implemented types

:   -   [Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

Annotations

:   -   \@Native(\"DOMRectReadOnly\")

Constructors
------------

[DomRectReadOnly](domrectreadonly/domrectreadonly)(\[[num](../dart-core/num-class)?
x, [num](../dart-core/num-class)? y, [num](../dart-core/num-class)?
width, [num](../dart-core/num-class)? height\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[bottom](domrectreadonly/bottom) → [num](../dart-core/num-class)

::: {.features}
read-only
:::

The y-coordinate of the bottom edge.

[bottomLeft](domrectreadonly/bottomleft) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[bottomRight](domrectreadonly/bottomright) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[hashCode](domrectreadonly/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only
:::

The hash code for this object.

[height](domrectreadonly/height) → [num](../dart-core/num-class)

::: {.features}
read-only, override
:::

The height of the rectangle.

[left](domrectreadonly/left) → [num](../dart-core/num-class)

::: {.features}
read-only, override
:::

The x-coordinate of the left edge.

[right](domrectreadonly/right) → [num](../dart-core/num-class)

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

[top](domrectreadonly/top) → [num](../dart-core/num-class)

::: {.features}
read-only, override
:::

The y-coordinate of the top edge.

[topLeft](domrectreadonly/topleft) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[topRight](domrectreadonly/topright) →
[Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>

::: {.features}
read-only
:::

[width](domrectreadonly/width) → [num](../dart-core/num-class)

::: {.features}
read-only, override
:::

The width of the rectangle.

[x](domrectreadonly/x) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[y](domrectreadonly/y) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[boundingBox](domrectreadonly/boundingbox)([Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>
other) →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>

Returns a new rectangle which completely contains `this` and `other`.

[containsPoint](domrectreadonly/containspoint)([Point](../dart-math/point-class)\<[num](../dart-core/num-class)\>
another) → [bool](../dart-core/bool-class)

Tests whether `another` is inside or along the edges of `this`.

[containsRectangle](domrectreadonly/containsrectangle)([Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>
another) → [bool](../dart-core/bool-class)

Tests whether `this` entirely contains `another`.

[intersection](domrectreadonly/intersection)([Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>
other) →
[Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>?

Computes the intersection of `this` and `other`.

[intersects](domrectreadonly/intersects)([Rectangle](../dart-math/rectangle-class)\<[num](../dart-core/num-class)\>
other) → [bool](../dart-core/bool-class)

Returns true if `this` intersects `other`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](domrectreadonly/tostring)() →
[String](../dart-core/string-class)

A string representation of this object.

Operators
---------

[operator ==](domrectreadonly/operator_equals)([Object](../dart-core/object-class) other) → [bool](../dart-core/bool-class)
:   The equality operator.

Static Methods
--------------

[fromRect](domrectreadonly/fromrect)(\[[Map](../dart-core/map-class)?
other\]) → [DomRectReadOnly](domrectreadonly-class)

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomRectReadOnly-class.html>
:::
