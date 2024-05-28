[dart:core](../dart-core/dart-core-library){._links-link}

RangeError class
================

Error thrown due to a value being outside a valid range.

Inheritance

:   -   [Object](object-class)
    -   [Error](error-class)
    -   [ArgumentError](argumenterror-class)
    -   RangeError

Implementers

:   -   [IndexError](indexerror-class)

Constructors
------------

[RangeError](rangeerror/rangeerror)(dynamic message)

Create a new [RangeError](rangeerror-class) with the given `message`.

[RangeError.index](rangeerror/rangeerror.index)([int](int-class) index,
dynamic indexable, \[[String](string-class)? name,
[String](string-class)? message, [int](int-class)? length\])

::: {.constructor-modifier .features}
factory
:::

Creates a new [RangeError](rangeerror-class) stating that `index` is not
a valid index into `indexable`.

[RangeError.range](rangeerror/rangeerror.range)([num](num-class)
invalidValue, [int](int-class)? minValue, [int](int-class)? maxValue,
\[[String](string-class)? name, [String](string-class)? message\])

Create a new [RangeError](rangeerror-class) for a value being outside
the valid range.

[RangeError.value](rangeerror/rangeerror.value)([num](num-class) value,
\[[String](string-class)? name, [String](string-class)? message\])

Create a new [RangeError](rangeerror-class) with a message for the given
`value`.

Properties {#instance-properties}
----------

[end](rangeerror/end) → [num](num-class)?

::: {.features}
final
:::

The maximum value that [value](rangeerror/rangeerror.value) is allowed
to assume.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[invalidValue](argumenterror/invalidvalue) → dynamic

::: {.features}
final, inherited
:::

The invalid value.

[message](argumenterror/message) → dynamic

::: {.features}
final, inherited
:::

Message describing the problem.

[name](argumenterror/name) → [String](string-class)?

::: {.features}
final, inherited
:::

Name of the invalid argument, if available.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[stackTrace](error/stacktrace) → [StackTrace](stacktrace-class)?

::: {.features}
read-only, inherited
:::

The stack trace at the point where this error was first thrown.

[start](rangeerror/start) → [num](num-class)?

::: {.features}
final
:::

The minimum value that [value](rangeerror/rangeerror.value) is allowed
to assume.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](argumenterror/tostring)() → [String](string-class)

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

[checkNotNegative](rangeerror/checknotnegative)([int](int-class) value, \[[String](string-class)? name, [String](string-class)? message\]) → [int](int-class)
:   Check that an integer value is non-negative.

[checkValidIndex](rangeerror/checkvalidindex)([int](int-class) index, dynamic indexable, \[[String](string-class)? name, [int](int-class)? length, [String](string-class)? message\]) → [int](int-class)
:   Check that `index` is a valid index into an indexable object.

[checkValidRange](rangeerror/checkvalidrange)([int](int-class) start, [int](int-class)? end, [int](int-class) length, \[[String](string-class)? startName, [String](string-class)? endName, [String](string-class)? message\]) → [int](int-class)
:   Check that a range represents a slice of an indexable object.

[checkValueInInterval](rangeerror/checkvalueininterval)([int](int-class) value, [int](int-class) minValue, [int](int-class) maxValue, \[[String](string-class)? name, [String](string-class)? message\]) → [int](int-class)
:   Check that an integer `value` lies in a specific interval.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/RangeError-class.html>
:::
