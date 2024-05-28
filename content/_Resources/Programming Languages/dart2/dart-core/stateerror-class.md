[dart:core](../dart-core/dart-core-library){._links-link}

StateError class
================

The operation was not allowed by the current state of the object.

Should be used when this particular object is currently in a state which
doesn\'t support the requested operation, but other similar objects
might, or the object might change its state to one which supports the
operation. Example: Asking for `list.first` on a currently empty list.
If the operation is never supported, consider using
[UnsupportedError](unsupportederror-class) instead.

This is a generic error used for a variety of different erroneous
actions. The message should be descriptive.

Inheritance

:   -   [Object](object-class)
    -   [Error](error-class)
    -   StateError

Constructors
------------

[StateError](stateerror/stateerror)([String](string-class) message)

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[message](stateerror/message) → [String](string-class)

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

[toString](stateerror/tostring)() → [String](string-class)

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
<https://api.dart.dev/stable/2.18.5/dart-core/StateError-class.html>
:::
