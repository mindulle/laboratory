[dart:developer](../dart-developer/dart-developer-library){._links-link}

Gauge class
===========

A measured value with a min and max. Initial value is min. Value will be
clamped to the interval `[min, max]`.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Metric](metric-class)
    -   Gauge

Constructors
------------

[Gauge](gauge/gauge)([String](../dart-core/string-class) name,
[String](../dart-core/string-class) description,
[double](../dart-core/double-class) min,
[double](../dart-core/double-class) max)

Properties {#instance-properties}
----------

[description](metric/description) → [String](../dart-core/string-class)

::: {.features}
final, inherited
:::

[description](metric/description) of this metric.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[max](gauge/max) → [double](../dart-core/double-class)

::: {.features}
final
:::

[min](gauge/min) → [double](../dart-core/double-class)

::: {.features}
final
:::

[name](metric/name) → [String](../dart-core/string-class)

::: {.features}
final, inherited
:::

[name](metric/name) of this metric.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[value](gauge/value) ↔ [double](../dart-core/double-class)

::: {.features}
read / write
:::

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

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
<https://api.dart.dev/stable/2.18.5/dart-developer/Gauge-class.html>
:::
