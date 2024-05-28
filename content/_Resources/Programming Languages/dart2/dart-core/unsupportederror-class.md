[dart:core](../dart-core/dart-core-library){._links-link}

UnsupportedError class
======================

The operation was not allowed by the object.

This [Error](error-class) is thrown when an instance cannot implement
one of the methods in its signature.

Inheritance

:   -   [Object](object-class)
    -   [Error](error-class)
    -   UnsupportedError

Implementers

:   -   [IntegerDivisionByZeroException](integerdivisionbyzeroexception-class){.deprecated}
    -   [UnimplementedError](unimplementederror-class)

Constructors
------------

[UnsupportedError](unsupportederror/unsupportederror)([String](string-class)
message)

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[message](unsupportederror/message) → [String](string-class)?

::: {.features}
final
:::

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

[toString](unsupportederror/tostring)() → [String](string-class)

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
<https://api.dart.dev/stable/2.18.5/dart-core/UnsupportedError-class.html>
:::
