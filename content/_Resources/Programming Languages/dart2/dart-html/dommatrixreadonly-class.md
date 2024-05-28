[dart:html](../dart-html/dart-html-library){._links-link}

DomMatrixReadOnly class
=======================

Implementers

:   -   [DomMatrix](dommatrix-class)

Annotations

:   -   \@Native(\"DOMMatrixReadOnly\")

Constructors
------------

[DomMatrixReadOnly](dommatrixreadonly/dommatrixreadonly)(\[[Object](../dart-core/object-class)?
init\])

::: {.constructor-modifier .features}
factory
:::

Properties {#instance-properties}
----------

[a](dommatrixreadonly/a) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[b](dommatrixreadonly/b) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[c](dommatrixreadonly/c) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[d](dommatrixreadonly/d) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[e](dommatrixreadonly/e) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[f](dommatrixreadonly/f) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[is2D](dommatrixreadonly/is2d) → [bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[isIdentity](dommatrixreadonly/isidentity) →
[bool](../dart-core/bool-class)?

::: {.features}
read-only
:::

[m11](dommatrixreadonly/m11) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m12](dommatrixreadonly/m12) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m13](dommatrixreadonly/m13) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m14](dommatrixreadonly/m14) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m21](dommatrixreadonly/m21) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m22](dommatrixreadonly/m22) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m23](dommatrixreadonly/m23) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m24](dommatrixreadonly/m24) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m31](dommatrixreadonly/m31) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m32](dommatrixreadonly/m32) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m33](dommatrixreadonly/m33) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m34](dommatrixreadonly/m34) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m41](dommatrixreadonly/m41) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m42](dommatrixreadonly/m42) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m43](dommatrixreadonly/m43) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[m44](dommatrixreadonly/m44) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[flipX](dommatrixreadonly/flipx)() → [DomMatrix](dommatrix-class)

[flipY](dommatrixreadonly/flipy)() → [DomMatrix](dommatrix-class)

[inverse](dommatrixreadonly/inverse)() → [DomMatrix](dommatrix-class)

[multiply](dommatrixreadonly/multiply)(\[[Map](../dart-core/map-class)?
other\]) → [DomMatrix](dommatrix-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[rotate](dommatrixreadonly/rotate)(\[[num](../dart-core/num-class)?
rotX, [num](../dart-core/num-class)? rotY,
[num](../dart-core/num-class)? rotZ\]) → [DomMatrix](dommatrix-class)

[rotateAxisAngle](dommatrixreadonly/rotateaxisangle)(\[[num](../dart-core/num-class)?
x, [num](../dart-core/num-class)? y, [num](../dart-core/num-class)? z,
[num](../dart-core/num-class)? angle\]) → [DomMatrix](dommatrix-class)

[rotateFromVector](dommatrixreadonly/rotatefromvector)(\[[num](../dart-core/num-class)?
x, [num](../dart-core/num-class)? y\]) → [DomMatrix](dommatrix-class)

[scale](dommatrixreadonly/scale)(\[[num](../dart-core/num-class)?
scaleX, [num](../dart-core/num-class)? scaleY,
[num](../dart-core/num-class)? scaleZ, [num](../dart-core/num-class)?
originX, [num](../dart-core/num-class)? originY,
[num](../dart-core/num-class)? originZ\]) → [DomMatrix](dommatrix-class)

[scale3d](dommatrixreadonly/scale3d)(\[[num](../dart-core/num-class)?
scale, [num](../dart-core/num-class)? originX,
[num](../dart-core/num-class)? originY, [num](../dart-core/num-class)?
originZ\]) → [DomMatrix](dommatrix-class)

[skewX](dommatrixreadonly/skewx)(\[[num](../dart-core/num-class)? sx\])
→ [DomMatrix](dommatrix-class)

[skewY](dommatrixreadonly/skewy)(\[[num](../dart-core/num-class)? sy\])
→ [DomMatrix](dommatrix-class)

[toFloat32Array](dommatrixreadonly/tofloat32array)() →
[Float32List](../dart-typed_data/float32list-class)

[toFloat64Array](dommatrixreadonly/tofloat64array)() →
[Float64List](../dart-typed_data/float64list-class)

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[transformPoint](dommatrixreadonly/transformpoint)(\[[Map](../dart-core/map-class)?
point\]) → [DomPoint](dompoint-class)

[translate](dommatrixreadonly/translate)(\[[num](../dart-core/num-class)?
tx, [num](../dart-core/num-class)? ty, [num](../dart-core/num-class)?
tz\]) → [DomMatrix](dommatrix-class)

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[fromFloat32Array](dommatrixreadonly/fromfloat32array)([Float32List](../dart-typed_data/float32list-class)
array32) → [DomMatrixReadOnly](dommatrixreadonly-class)

[fromFloat64Array](dommatrixreadonly/fromfloat64array)([Float64List](../dart-typed_data/float64list-class)
array64) → [DomMatrixReadOnly](dommatrixreadonly-class)

[fromMatrix](dommatrixreadonly/frommatrix)(\[[Map](../dart-core/map-class)?
other\]) → [DomMatrixReadOnly](dommatrixreadonly-class)

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomMatrixReadOnly-class.html>
:::
