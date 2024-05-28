[dart:html](../dart-html/dart-html-library){._links-link}

DomPoint class
==============

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [DomPointReadOnly](dompointreadonly-class)
    -   DomPoint

Annotations

:   -   \@Native(\"DOMPoint\")

Constructors
------------

[DomPoint](dompoint/dompoint)(\[[num](../dart-core/num-class)? x,
[num](../dart-core/num-class)? y, [num](../dart-core/num-class)? z,
[num](../dart-core/num-class)? w\])

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

[w](dompoint/w) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write, override-getter
:::

[x](dompoint/x) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write, override-getter
:::

[y](dompoint/y) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write, override-getter
:::

[z](dompoint/z) ↔ [num](../dart-core/num-class)?

::: {.features}
read / write, override-getter
:::

Methods {#instance-methods}
-------

[matrixTransform](dompointreadonly/matrixtransform)(\[[Map](../dart-core/map-class)?
matrix\]) → [DomPoint](dompoint-class)

::: {.features}
inherited
:::

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

Static Properties
-----------------

[supported](dompoint/supported) → [bool](../dart-core/bool-class)

::: {.features}
read-only
:::

Checks if this type is supported on the current platform.

Static Methods
--------------

[fromPoint](dompoint/frompoint)(\[[Map](../dart-core/map-class)?
other\]) → [DomPoint](dompoint-class)

::: {.features}
override
:::

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/DomPoint-class.html>
:::
