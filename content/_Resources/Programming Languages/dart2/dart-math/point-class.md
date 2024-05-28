[dart:math](../dart-math/dart-math-library){._links-link}

Point\<T extends num\> class
============================

A utility class for representing two-dimensional positions.

Example:

``` {.language-dart data-language="dart"}
var leftTop = const Point(0, 0);
var rightBottom = const Point(200, 400);
```

Constructors
------------

[Point](point/point)(T x, T y)

::: {.constructor-modifier .features}
const
:::

Creates a point with the provided `x` and `y` coordinates.

Properties {#instance-properties}
----------

[hashCode](point/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

The hash code for this object.

[magnitude](point/magnitude) → [double](../dart-core/double-class)

::: {.features}
read-only
:::

Get the straight line (Euclidean) distance between the origin (0, 0) and
this point.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[x](point/x) → T

::: {.features}
final
:::

[y](point/y) → T

::: {.features}
final
:::

Methods {#instance-methods}
-------

[distanceTo](point/distanceto)([Point](point-class)\<T\> other) →
[double](../dart-core/double-class)

Returns the distance between `this` and `other`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[squaredDistanceTo](point/squareddistanceto)([Point](point-class)\<T\>
other) → T

Returns the squared distance between `this` and `other`.

[toString](point/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

A string representation of this object.

Operators
---------

[operator \*](point/operator_multiply)([num](../dart-core/num-class)
factor) → [Point](point-class)\<T\>

Scale this point by `factor` as if it were a vector.

[operator +](point/operator_plus)([Point](point-class)\<T\> other) →
[Point](point-class)\<T\>

Add `other` to `this`, as if both points were vectors.

[operator -](point/operator_minus)([Point](point-class)\<T\> other) →
[Point](point-class)\<T\>

Subtract `other` from `this`, as if both points were vectors.

[operator ==](point/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Whether `other` is a point with the same coordinates as this point.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-math/Point-class.html>
:::
