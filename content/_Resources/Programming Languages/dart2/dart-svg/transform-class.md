[dart:svg](../dart-svg/dart-svg-library){._links-link}

Transform class
===============

Annotations

:   -   \@Unstable()
    -   \@Native(\"SVGTransform\")

Properties {#instance-properties}
----------

[angle](transform/angle) → [num](../dart-core/num-class)?

::: {.features}
read-only
:::

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[matrix](transform/matrix) → [Matrix](matrix-class)?

::: {.features}
read-only
:::

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[type](transform/type) → [int](../dart-core/int-class)?

::: {.features}
read-only
:::

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[setMatrix](transform/setmatrix)([Matrix](matrix-class) matrix) → void

[setRotate](transform/setrotate)([num](../dart-core/num-class) angle,
[num](../dart-core/num-class) cx, [num](../dart-core/num-class) cy) →
void

[setScale](transform/setscale)([num](../dart-core/num-class) sx,
[num](../dart-core/num-class) sy) → void

[setSkewX](transform/setskewx)([num](../dart-core/num-class) angle) →
void

[setSkewY](transform/setskewy)([num](../dart-core/num-class) angle) →
void

[setTranslate](transform/settranslate)([num](../dart-core/num-class) tx,
[num](../dart-core/num-class) ty) → void

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

Constants
---------

[SVG\_TRANSFORM\_MATRIX](transform/svg_transform_matrix-constant) → const [int](../dart-core/int-class)

:   <div>

    `1`

    </div>

[SVG\_TRANSFORM\_ROTATE](transform/svg_transform_rotate-constant) → const [int](../dart-core/int-class)

:   <div>

    `4`

    </div>

[SVG\_TRANSFORM\_SCALE](transform/svg_transform_scale-constant) → const [int](../dart-core/int-class)

:   <div>

    `3`

    </div>

[SVG\_TRANSFORM\_SKEWX](transform/svg_transform_skewx-constant) → const [int](../dart-core/int-class)

:   <div>

    `5`

    </div>

[SVG\_TRANSFORM\_SKEWY](transform/svg_transform_skewy-constant) → const [int](../dart-core/int-class)

:   <div>

    `6`

    </div>

[SVG\_TRANSFORM\_TRANSLATE](transform/svg_transform_translate-constant) → const [int](../dart-core/int-class)

:   <div>

    `2`

    </div>

[SVG\_TRANSFORM\_UNKNOWN](transform/svg_transform_unknown-constant) → const [int](../dart-core/int-class)

:   <div>

    `0`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-svg/Transform-class.html>
:::
