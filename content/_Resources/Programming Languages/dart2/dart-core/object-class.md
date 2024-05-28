[dart:core](../dart-core/dart-core-library){._links-link}

Object class
============

The base class for all Dart objects except `null`.

Because `Object` is a root of the non-nullable Dart class hierarchy,
every other non-`Null` Dart class is a subclass of `Object`.

When you define a class, you should consider overriding
[toString](object/tostring) to return a string describing an instance of
that class. You might also need to define [hashCode](object/hashcode)
and [operator ==](object/operator_equals), as described in the
[Implementing map
keys](https://dart.dev/guides/libraries/library-tour#implementing-map-keys)
section of the [library
tour](https://dart.dev/guides/libraries/library-tour).

Constructors
------------

[Object](object/object)()

::: {.constructor-modifier .features}
const
:::

Creates a new [Object](object-class) instance.

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only
:::

The hash code for this object.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class) invocation) → dynamic
:   Invoked when a non-existent method or property is accessed.

[toString](object/tostring)() → [String](string-class)
:   A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) → [bool](bool-class)
:   The equality operator.

Static Methods
--------------

[hash](object/hash)([Object](object-class)? object1,
[Object](object-class)? object2, \[[Object](object-class)? object3 =
sentinelValue, [Object](object-class)? object4 = sentinelValue,
[Object](object-class)? object5 = sentinelValue, [Object](object-class)?
object6 = sentinelValue, [Object](object-class)? object7 =
sentinelValue, [Object](object-class)? object8 = sentinelValue,
[Object](object-class)? object9 = sentinelValue, [Object](object-class)?
object10 = sentinelValue, [Object](object-class)? object11 =
sentinelValue, [Object](object-class)? object12 = sentinelValue,
[Object](object-class)? object13 = sentinelValue,
[Object](object-class)? object14 = sentinelValue,
[Object](object-class)? object15 = sentinelValue,
[Object](object-class)? object16 = sentinelValue,
[Object](object-class)? object17 = sentinelValue,
[Object](object-class)? object18 = sentinelValue,
[Object](object-class)? object19 = sentinelValue,
[Object](object-class)? object20 = sentinelValue\]) → [int](int-class)

::: {.features}
\@Since(\"2.14\")
:::

Creates a combined hash code for a number of objects.

[hashAll](object/hashall)([Iterable](iterable-class)\<[Object](object-class)?\>
objects) → [int](int-class)

::: {.features}
\@Since(\"2.14\")
:::

Creates a combined hash code for a sequence of objects.

[hashAllUnordered](object/hashallunordered)([Iterable](iterable-class)\<[Object](object-class)?\>
objects) → [int](int-class)

::: {.features}
\@Since(\"2.14\")
:::

Creates a combined hash code for a collection of objects.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Object-class.html>
:::
