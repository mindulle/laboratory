[dart:convert](../dart-convert/dart-convert-library){._links-link}

ChunkedConversionSink\<T\> class
================================

A [ChunkedConversionSink](chunkedconversionsink-class) is used to
transmit data more efficiently between two converters during chunked
conversions.

The basic `ChunkedConversionSink` is just a
[Sink](../dart-core/sink-class), and converters should work with a plain
`Sink`, but may work more efficiently with certain specialized types of
`ChunkedConversionSink`.

It is recommended that implementations of `ChunkedConversionSink` extend
this class, to inherit any further methods that may be added to the
class.

Implemented types

:   -   [Sink](../dart-core/sink-class)\<T\>

Implementers

:   -   [ByteConversionSink](byteconversionsink-class)
    -   [StringConversionSink](stringconversionsink-class)

Constructors
------------

[ChunkedConversionSink](chunkedconversionsink/chunkedconversionsink)()

[ChunkedConversionSink.withCallback](chunkedconversionsink/chunkedconversionsink.withcallback)(void
callback([List](../dart-core/list-class)\<T\> accumulated))

::: {.constructor-modifier .features}
factory
:::

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

[add](chunkedconversionsink/add)(T chunk) → void

::: {.features}
override
:::

Adds chunked data to this sink.

[close](chunkedconversionsink/close)() → void

::: {.features}
override
:::

Closes the sink.

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
<https://api.dart.dev/stable/2.18.5/dart-convert/ChunkedConversionSink-class.html>
:::
