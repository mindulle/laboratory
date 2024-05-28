[dart:html](../dart-html/dart-html-library){._links-link}

Path2D class
============

Annotations

:   -   \@Native(\"Path2D\")

Constructors
------------

[Path2D](path2d/path2d)(\[dynamic path\_OR\_text\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[addPath](path2d/addpath)([Path2D](path2d-class) path,
\[[Matrix](../dart-svg/matrix-class)? transform\]) → void

[arc](path2d/arc)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y, [num](../dart-core/num-class) radius,
[num](../dart-core/num-class) startAngle, [num](../dart-core/num-class)
endAngle, [bool](../dart-core/bool-class)? anticlockwise) → void

[arcTo](path2d/arcto)([num](../dart-core/num-class) x1,
[num](../dart-core/num-class) y1, [num](../dart-core/num-class) x2,
[num](../dart-core/num-class) y2, [num](../dart-core/num-class) radius)
→ void

[bezierCurveTo](path2d/beziercurveto)([num](../dart-core/num-class)
cp1x, [num](../dart-core/num-class) cp1y, [num](../dart-core/num-class)
cp2x, [num](../dart-core/num-class) cp2y, [num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → void

[closePath](path2d/closepath)() → void

[ellipse](path2d/ellipse)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y, [num](../dart-core/num-class) radiusX,
[num](../dart-core/num-class) radiusY, [num](../dart-core/num-class)
rotation, [num](../dart-core/num-class) startAngle,
[num](../dart-core/num-class) endAngle, [bool](../dart-core/bool-class)?
anticlockwise) → void

[lineTo](path2d/lineto)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y) → void

[moveTo](path2d/moveto)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y) → void

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[quadraticCurveTo](path2d/quadraticcurveto)([num](../dart-core/num-class)
cpx, [num](../dart-core/num-class) cpy, [num](../dart-core/num-class) x,
[num](../dart-core/num-class) y) → void

[rect](path2d/rect)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y, [num](../dart-core/num-class) width,
[num](../dart-core/num-class) height) → void

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Path2D-class.html>
:::
