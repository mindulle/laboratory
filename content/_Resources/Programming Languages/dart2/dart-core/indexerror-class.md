[dart:core](../dart-core/dart-core-library){._links-link}

IndexError class
================

A specialized [RangeError](rangeerror-class) used when an index is not
in the range `0..indexable.length-1`.

Also contains the indexable object, its length at the time of the error,
and the invalid index itself.

Inheritance

:   -   [Object](object-class)
    -   [Error](error-class)
    -   [ArgumentError](argumenterror-class)
    -   IndexError

Implemented types

:   -   [RangeError](rangeerror-class)

Constructors
------------

[IndexError](indexerror/indexerror)([int](int-class) invalidValue, dynamic indexable, \[[String](string-class)? name, [String](string-class)? message, [int](int-class)? length\])
:   Creates a new [IndexError](indexerror-class) stating that
    `invalidValue` is not a valid index into `indexable`.

Properties {#instance-properties}
----------

[end](indexerror/end) → [int](int-class)

::: {.features}
read-only, override
:::

The maximum value that [value](argumenterror/argumenterror.value) is
allowed to assume.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[indexable](indexerror/indexable) → dynamic

::: {.features}
final
:::

The indexable object that [invalidValue](argumenterror/invalidvalue) was
not a valid index into.

[invalidValue](argumenterror/invalidvalue) → dynamic

::: {.features}
final, inherited
:::

The invalid value.

[length](indexerror/length) → [int](int-class)

::: {.features}
final
:::

The length of [indexable](indexerror/indexable) at the time of the
error.

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

[start](indexerror/start) → [int](int-class)

::: {.features}
read-only, override
:::

The minimum value that [value](argumenterror/argumenterror.value) is
allowed to assume.

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/IndexError-class.html>
:::
