[dart:core](../dart-core/dart-core-library){._links-link}

Exception class
===============

A marker interface implemented by all core library exceptions.

An [Exception](exception-class) is intended to convey information to the
user about a failure, so that the error can be addressed
programmatically. It is intended to be caught, and it should contain
useful data fields.

Creating instances of [Exception](exception-class) directly with
`Exception("message")` is discouraged in library code since it doesn\'t
give users a precise type they can catch. It may be reasonable to use
instances of this class in tests or during development.

Implementers

:   -   [DeferredLoadException](../dart-async/deferredloadexception-class)
    -   [FormatException](formatexception-class)
    -   [IntegerDivisionByZeroException](integerdivisionbyzeroexception-class){.deprecated}
    -   [IOException](../dart-io/ioexception-class)
    -   [IsolateSpawnException](../dart-isolate/isolatespawnexception-class)
    -   [NullRejectionException](../dart-js_util/nullrejectionexception-class)
    -   [OSError](../dart-io/oserror-class)
    -   [TimeoutException](../dart-async/timeoutexception-class)

Constructors
------------

[Exception](exception/exception)(\[dynamic message\])

::: {.constructor-modifier .features}
factory
:::

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

[toString](object/tostring)() → [String](string-class)

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
<https://api.dart.dev/stable/2.18.5/dart-core/Exception-class.html>
:::
