[dart:core](../dart-core/dart-core-library){._links-link}

ConcurrentModificationError class
=================================

Error occurring when a collection is modified during iteration.

Some modifications may be allowed for some collections, so each
collection ([Iterable](iterable-class) or similar collection of values)
should declare which operations are allowed during an iteration.

Inheritance

:   -   [Object](object-class)
    -   [Error](error-class)
    -   ConcurrentModificationError

Constructors
------------

[ConcurrentModificationError](concurrentmodificationerror/concurrentmodificationerror)(\[[Object](object-class)?
modifiedObject\])

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[modifiedObject](concurrentmodificationerror/modifiedobject) →
[Object](object-class)?

::: {.features}
final
:::

The object that was modified in an incompatible way.

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

[toString](concurrentmodificationerror/tostring)() →
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
<https://api.dart.dev/stable/2.18.5/dart-core/ConcurrentModificationError-class.html>
:::
