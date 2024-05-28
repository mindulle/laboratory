[dart:svg](../dart-svg/dart-svg-library){._links-link}

Matrix class
============

Annotations

:   -   \@Unstable()
    -   \@Native(\"SVGMatrix\")

Properties {#instance-properties}
----------

[a](matrix/a) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[b](matrix/b) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[c](matrix/c) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[d](matrix/d) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[e](matrix/e) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

[f](matrix/f) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write
:::

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

[flipX](matrix/flipx)() → [Matrix](matrix-class)

[flipY](matrix/flipy)() → [Matrix](matrix-class)

[inverse](matrix/inverse)() → [Matrix](matrix-class)

[multiply](matrix/multiply)([Matrix](matrix-class) secondMatrix) →
[Matrix](matrix-class)

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[rotate](matrix/rotate)([num](../dart-core/num-class) angle) →
[Matrix](matrix-class)

[rotateFromVector](matrix/rotatefromvector)([num](../dart-core/num-class)
x, [num](../dart-core/num-class) y) → [Matrix](matrix-class)

[scale](matrix/scale)([num](../dart-core/num-class) scaleFactor) →
[Matrix](matrix-class)

[scaleNonUniform](matrix/scalenonuniform)([num](../dart-core/num-class)
scaleFactorX, [num](../dart-core/num-class) scaleFactorY) →
[Matrix](matrix-class)

[skewX](matrix/skewx)([num](../dart-core/num-class) angle) →
[Matrix](matrix-class)

[skewY](matrix/skewy)([num](../dart-core/num-class) angle) →
[Matrix](matrix-class)

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[translate](matrix/translate)([num](../dart-core/num-class) x,
[num](../dart-core/num-class) y) → [Matrix](matrix-class)

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
<https://api.dart.dev/stable/2.18.5/dart-svg/Matrix-class.html>
:::
