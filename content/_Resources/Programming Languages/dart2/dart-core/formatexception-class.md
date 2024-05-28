[dart:core](../dart-core/dart-core-library){._links-link}

FormatException class
=====================

Exception thrown when a string or some other data does not have an
expected format and cannot be parsed or processed.

Implemented types

:   -   [Exception](exception-class)

Constructors
------------

[FormatException](formatexception/formatexception)(\[[String](string-class)
message = \"\", dynamic source, [int](int-class)? offset\])

::: {.constructor-modifier .features}
const
:::

Creates a new `FormatException` with an optional error
[message](formatexception/message).

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[message](formatexception/message) → [String](string-class)

::: {.features}
final
:::

A message describing the format error.

[offset](formatexception/offset) → [int](int-class)?

::: {.features}
final
:::

The offset in [source](formatexception/source) where the error was
detected.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[source](formatexception/source) → dynamic

::: {.features}
final
:::

The actual source input which caused the error.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](formatexception/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns a description of the format exception.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/FormatException-class.html>
:::
