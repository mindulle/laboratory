[dart:convert](../dart-convert/dart-convert-library){._links-link}

JsonCyclicError class
=====================

Reports that an object could not be stringified due to cyclic
references.

An object that references itself cannot be serialized by
[JsonCodec.encode](jsoncodec/encode)/[JsonEncoder.convert](jsonencoder/convert).
When the cycle is detected, a [JsonCyclicError](jsoncyclicerror-class)
is thrown.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Error](../dart-core/error-class)
    -   [JsonUnsupportedObjectError](jsonunsupportedobjecterror-class)
    -   JsonCyclicError

Constructors
------------

[JsonCyclicError](jsoncyclicerror/jsoncyclicerror)([Object](../dart-core/object-class)? object)
:   The first object that was detected as part of a cycle.

Properties {#instance-properties}
----------

[cause](jsonunsupportedobjecterror/cause) →
[Object](../dart-core/object-class)?

::: {.features}
final, inherited
:::

The exception thrown when trying to convert the object.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[partialResult](jsonunsupportedobjecterror/partialresult) →
[String](../dart-core/string-class)?

::: {.features}
final, inherited
:::

The partial result of the conversion, up until the error happened.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[stackTrace](../dart-core/error/stacktrace) →
[StackTrace](../dart-core/stacktrace-class)?

::: {.features}
read-only, inherited
:::

The stack trace at the point where this error was first thrown.

[unsupportedObject](jsonunsupportedobjecterror/unsupportedobject) →
[Object](../dart-core/object-class)?

::: {.features}
final, inherited
:::

The object that could not be serialized.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](jsoncyclicerror/tostring)() →
[String](../dart-core/string-class)

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
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonCyclicError-class.html>
:::
