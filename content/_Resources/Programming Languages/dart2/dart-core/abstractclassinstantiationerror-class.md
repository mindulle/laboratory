[dart:core](../dart-core/dart-core-library){._links-link}

AbstractClassInstantiationError class
=====================================

Error thrown when trying to instantiate an abstract class.

No longer used in Dart 2 where it has become a compile-time error to
call the constructor of an abstract class.

Inheritance

:   -   [Object](object-class)
    -   [Error](error-class)
    -   AbstractClassInstantiationError

Annotations

:   -   @[Deprecated](deprecated-class)(\"No longer relevant in Dart
        2.0\")

Constructors
------------

[AbstractClassInstantiationError](abstractclassinstantiationerror/abstractclassinstantiationerror)([String](string-class)
className)

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

[toString](abstractclassinstantiationerror/tostring)() →
[String](string-class)

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
<https://api.dart.dev/stable/2.18.5/dart-core/AbstractClassInstantiationError-class.html>
:::
