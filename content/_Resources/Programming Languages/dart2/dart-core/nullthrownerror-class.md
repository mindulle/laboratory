[dart:core](../dart-core/dart-core-library){._links-link}

NullThrownError class
=====================

Error thrown when attempting to throw `null`.

In null safe code, you are statically disallowed from throwing `null`,
so this error will go away when non-null safe code stops being
supported.

Inheritance

:   -   [Object](object-class)
    -   [Error](error-class)
    -   NullThrownError

Constructors
------------

[NullThrownError](nullthrownerror/nullthrownerror)()

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

[toString](nullthrownerror/tostring)() → [String](string-class)

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/NullThrownError-class.html>
:::
