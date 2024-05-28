[dart:convert](../dart-convert/dart-convert-library){._links-link}

ByteConversionSink class
========================

The [ByteConversionSink](byteconversionsink-class) provides an interface
for converters to efficiently transmit byte data.

Instead of limiting the interface to one non-chunked list of bytes it
accepts its input in chunks (themselves being lists of bytes).

This abstract class will likely get more methods over time. Implementers
are urged to extend or mix in
[ByteConversionSinkBase](byteconversionsinkbase-class) to ensure that
their class covers the newly added methods.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [ChunkedConversionSink](chunkedconversionsink-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   ByteConversionSink

Implementers

:   -   [ByteConversionSinkBase](byteconversionsinkbase-class)

Constructors
------------

[ByteConversionSink](byteconversionsink/byteconversionsink)()

[ByteConversionSink.from](byteconversionsink/byteconversionsink.from)([Sink](../dart-core/sink-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
sink)

::: {.constructor-modifier .features}
factory
:::

[ByteConversionSink.withCallback](byteconversionsink/byteconversionsink.withcallback)(void
callback([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
accumulated))

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

[add](chunkedconversionsink/add)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
chunk) → void

::: {.features}
inherited
:::

Adds chunked data to this sink.

[addSlice](byteconversionsink/addslice)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
chunk, [int](../dart-core/int-class) start,
[int](../dart-core/int-class) end, [bool](../dart-core/bool-class)
isLast) → void

Adds the next `chunk` to `this`.

[close](chunkedconversionsink/close)() → void

::: {.features}
inherited
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
<https://api.dart.dev/stable/2.18.5/dart-convert/ByteConversionSink-class.html>
:::
