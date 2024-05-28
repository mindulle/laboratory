[dart:core](../dart-core/dart-core-library){._links-link}

NoSuchMethodError class
=======================

Error thrown by the default implementation of `noSuchMethod` on
[Object](object-class).

Inheritance

:   -   [Object](object-class)
    -   [Error](error-class)
    -   NoSuchMethodError

Constructors
------------

[NoSuchMethodError](nosuchmethoderror/nosuchmethoderror){.deprecated}([Object](object-class)?
receiver, [Symbol](symbol-class) memberName, [List](list-class)?
positionalArguments, [Map](map-class)\<[Symbol](symbol-class),
dynamic\>? namedArguments)

Create a [NoSuchMethodError](nosuchmethoderror-class) corresponding to a
failed method call.

[NoSuchMethodError.withInvocation](nosuchmethoderror/nosuchmethoderror.withinvocation)([Object](object-class)?
receiver, [Invocation](invocation-class) invocation)

::: {.constructor-modifier .features}
factory
:::

Creates a [NoSuchMethodError](nosuchmethoderror-class) corresponding to
a failed method call.

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

[toString](nosuchmethoderror/tostring)() → [String](string-class)

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
<https://api.dart.dev/stable/2.18.5/dart-core/NoSuchMethodError-class.html>
:::
