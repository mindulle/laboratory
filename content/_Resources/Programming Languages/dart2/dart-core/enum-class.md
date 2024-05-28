[dart:core](../dart-core/dart-core-library){._links-link}

Enum class
==========

An enumerated value.

This class is implemented by all types and values introduced using an
`enum` declaration. Non-platform classes cannot implement, extend or mix
in this class.

Available Extensions

:   -   [EnumName](enumname)

Annotations

:   -   \@Since(\"2.14\")

Constructors
------------

[Enum](enum/enum)()

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[index](enum/index) → [int](int-class)

::: {.features}
read-only
:::

A numeric identifier for the enumerated value.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[compareByIndex](enum/comparebyindex)\<T extends [Enum](enum-class)\>(T
value1, T value2) → [int](int-class)

::: {.features}
\@Since(\"2.15\")
:::

Compares two enum values by their [index](enum/index).

[compareByName](enum/comparebyname)\<T extends [Enum](enum-class)\>(T
value1, T value2) → [int](int-class)

::: {.features}
\@Since(\"2.15\")
:::

Compares enum values by name.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Enum-class.html>
:::
