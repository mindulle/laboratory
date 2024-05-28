[dart:isolate](../dart-isolate/dart-isolate-library){._links-link}

RemoteError class
=================

Description of an error from another isolate.

This error has the same `toString()` and `stackTrace.toString()`
behavior as the original error, but has no other features of the
original error.

Implemented types

:   -   [Error](../dart-core/error-class)

Constructors
------------

[RemoteError](remoteerror/remoteerror)([String](../dart-core/string-class)
description, [String](../dart-core/string-class) stackDescription)

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

[stackTrace](remoteerror/stacktrace) →
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

[toString](remoteerror/tostring)() → [String](../dart-core/string-class)

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-isolate/RemoteError-class.html>
:::
