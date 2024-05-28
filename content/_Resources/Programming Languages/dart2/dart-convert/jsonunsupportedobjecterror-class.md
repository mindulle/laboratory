[dart:convert](../dart-convert/dart-convert-library){._links-link}

JsonUnsupportedObjectError class
================================

Error thrown by JSON serialization if an object cannot be serialized.

The [unsupportedObject](jsonunsupportedobjecterror/unsupportedobject)
field holds that object that failed to be serialized.

If an object isn\'t directly serializable, the serializer calls the
`toJson` method on the object. If that call fails, the error will be
stored in the [cause](jsonunsupportedobjecterror/cause) field. If the
call returns an object that isn\'t directly serializable, the
[cause](jsonunsupportedobjecterror/cause) is null.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Error](../dart-core/error-class)
    -   JsonUnsupportedObjectError

Implementers

:   -   [JsonCyclicError](jsoncyclicerror-class)

Constructors
------------

[JsonUnsupportedObjectError](jsonunsupportedobjecterror/jsonunsupportedobjecterror)([Object](../dart-core/object-class)?
unsupportedObject, {[Object](../dart-core/object-class)? cause,
[String](../dart-core/string-class)? partialResult})

Properties {#instance-properties}
----------

[cause](jsonunsupportedobjecterror/cause) →
[Object](../dart-core/object-class)?

::: {.features}
final
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
final
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
final
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

[toString](jsonunsupportedobjecterror/tostring)() →
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
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonUnsupportedObjectError-class.html>
:::
