[dart:async](../dart-async/dart-async-library){._links-link}

AsyncError class
================

An error and a stack trace.

Used when an error and stack trace need to be handled as a single value,
for example when returned by [Zone.errorCallback](zone/errorcallback).

Implemented types

:   -   [Error](../dart-core/error-class)

Constructors
------------

[AsyncError](asyncerror/asyncerror)([Object](../dart-core/object-class)
error, [StackTrace](../dart-core/stacktrace-class)? stackTrace)

Properties {#instance-properties}
----------

[error](asyncerror/error) → [Object](../dart-core/object-class)

::: {.features}
final
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

[stackTrace](asyncerror/stacktrace) →
[StackTrace](../dart-core/stacktrace-class)

::: {.features}
final
:::

The stack trace at the point where this error was first thrown.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](asyncerror/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
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

Static Methods
--------------

[defaultStackTrace](asyncerror/defaultstacktrace)([Object](../dart-core/object-class) error) → [StackTrace](../dart-core/stacktrace-class)
:   A default stack trace for an error.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/AsyncError-class.html>
:::
