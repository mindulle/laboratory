[dart:convert](../dart-convert/dart-convert-library){._links-link}

ClosableStringSink class
========================

A [ClosableStringSink](closablestringsink-class) extends the
[StringSink](../dart-core/stringsink-class) interface by adding a
`close` method.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StringSink](../dart-core/stringsink-class)
    -   ClosableStringSink

Constructors
------------

[ClosableStringSink.fromStringSink](closablestringsink/closablestringsink.fromstringsink)([StringSink](../dart-core/stringsink-class)
sink, void onClose())

::: {.constructor-modifier .features}
factory
:::

Creates a new instance combining a
[StringSink](../dart-core/stringsink-class) `sink` and a callback
`onClose` which is invoked when the returned instance is closed.

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[close](closablestringsink/close)() → void

Closes `this` and flushes any outstanding data.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

[write](../dart-core/stringsink/write)([Object](../dart-core/object-class)?
object) → void

::: {.features}
inherited
:::

Writes the string representation of `object`.

[writeAll](../dart-core/stringsink/writeall)([Iterable](../dart-core/iterable-class)
objects, \[[String](../dart-core/string-class) separator = \"\"\]) →
void

::: {.features}
inherited
:::

Iterates over the given `objects` and
[write](../dart-core/stringsink/write)s them in sequence.

[writeCharCode](../dart-core/stringsink/writecharcode)([int](../dart-core/int-class)
charCode) → void

::: {.features}
inherited
:::

Writes the character represented by `charCode`.

[writeln](../dart-core/stringsink/writeln)(\[[Object](../dart-core/object-class)?
object = \"\"\]) → void

::: {.features}
inherited
:::

Writes `object` followed by a newline, `"\n"`.

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
<https://api.dart.dev/stable/2.18.5/dart-convert/ClosableStringSink-class.html>
:::
