[dart:core](../dart-core/dart-core-library){._links-link}

ArgumentError class
===================

Error thrown when a function is passed an unacceptable argument.

Inheritance

:   -   [Object](object-class)
    -   [Error](error-class)
    -   ArgumentError

Implementers

:   -   [IndexError](indexerror-class)
    -   [RangeError](rangeerror-class)

Constructors
------------

[ArgumentError](argumenterror/argumenterror)(\[dynamic message, \@Since(\"2.14\") [String](string-class)? name\])
:   Creates an error with [message](argumenterror/message) describing
    the problem with an argument.

[ArgumentError.notNull](argumenterror/argumenterror.notnull)(\[[String](string-class)? name\])
:   Creates an argument error for a `null` argument that must not be
    `null`.

[ArgumentError.value](argumenterror/argumenterror.value)(dynamic value, \[[String](string-class)? name, dynamic message\])
:   Creates error containing the invalid `value`.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[invalidValue](argumenterror/invalidvalue) → dynamic

::: {.features}
final
:::

The invalid value.

[message](argumenterror/message) → dynamic

::: {.features}
final
:::

Message describing the problem.

[name](argumenterror/name) → [String](string-class)?

::: {.features}
final
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
override
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

[checkNotNull](argumenterror/checknotnull)\<\@Since(\"2.8\") T\>(T?
argument, \[[String](string-class)? name\]) → T

::: {.features}
\@Since(\"2.1\")
:::

Throws if `argument` is `null`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/ArgumentError-class.html>
:::
