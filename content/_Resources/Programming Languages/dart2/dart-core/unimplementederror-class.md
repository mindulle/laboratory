[dart:core](../dart-core/dart-core-library){._links-link}

UnimplementedError class
========================

Thrown by operations that have not been implemented yet.

This [Error](error-class) is thrown by unfinished code that hasn\'t yet
implemented all the features it needs.

If the class does not intend to implement the feature, it should throw
an [UnsupportedError](unsupportederror-class) instead. This error is
only intended for use during development.

Inheritance

:   -   [Object](object-class)
    -   [Error](error-class)
    -   UnimplementedError

Implemented types

:   -   [UnsupportedError](unsupportederror-class)

Constructors
------------

[UnimplementedError](unimplementederror/unimplementederror)(\[[String](string-class)?
message\])

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[message](unimplementederror/message) → [String](string-class)?

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

[toString](unimplementederror/tostring)() → [String](string-class)

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
<https://api.dart.dev/stable/2.18.5/dart-core/UnimplementedError-class.html>
:::
