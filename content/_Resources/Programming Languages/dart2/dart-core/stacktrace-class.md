[dart:core](../dart-core/dart-core-library){._links-link}

StackTrace class
================

An interface implemented by all stack trace objects.

A [StackTrace](stacktrace-class) is intended to convey information to
the user about the call sequence that triggered an exception.

These objects are created by the runtime, it is not possible to create
them programmatically.

Constructors
------------

[StackTrace](stacktrace/stacktrace)()

[StackTrace.fromString](stacktrace/stacktrace.fromstring)([String](string-class)
stackTraceString)

::: {.constructor-modifier .features}
factory
:::

Create a `StackTrace` object from `stackTraceString`.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

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

[toString](stacktrace/tostring)() → [String](string-class)

::: {.features}
override
:::

Returns a [String](string-class) representation of the stack trace.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Properties
-----------------

[current](stacktrace/current) → [StackTrace](stacktrace-class)

::: {.features}
read-only
:::

Returns a representation of the current stack trace.

Constants
---------

[empty](stacktrace/empty-constant) → const \_StringStackTrace

::: {.features}
\@Since(\"2.8\")
:::

A stack trace object with no information.

<div>

`const _StringStackTrace("")`

</div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/StackTrace-class.html>
:::
