[dart:convert](../dart-convert/dart-convert-library){._links-link}

StringConversionSink class
==========================

This class provides an interface for converters to efficiently transmit
String data.

Instead of limiting the interface to one non-chunked String it accepts
partial strings or can be transformed into a byte sink that accepts
UTF-8 code units.

This abstract class will likely get more methods over time. Implementers
are urged to extend
[StringConversionSinkBase](stringconversionsinkbase-class) or to mix in
[StringConversionSinkMixin](stringconversionsinkmixin-class), to ensure
that their class covers the newly added methods.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [ChunkedConversionSink](chunkedconversionsink-class)\<[String](../dart-core/string-class)\>
    -   StringConversionSink

Implementers

:   -   [StringConversionSinkMixin](stringconversionsinkmixin-class)

Constructors
------------

[StringConversionSink](stringconversionsink/stringconversionsink)()

[StringConversionSink.from](stringconversionsink/stringconversionsink.from)([Sink](../dart-core/sink-class)\<[String](../dart-core/string-class)\>
sink)

::: {.constructor-modifier .features}
factory
:::

[StringConversionSink.fromStringSink](stringconversionsink/stringconversionsink.fromstringsink)([StringSink](../dart-core/stringsink-class)
sink)

::: {.constructor-modifier .features}
factory
:::

Creates a new instance wrapping the given `sink`.

[StringConversionSink.withCallback](stringconversionsink/stringconversionsink.withcallback)(void
callback([String](../dart-core/string-class) accumulated))

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

[add](chunkedconversionsink/add)([String](../dart-core/string-class)
chunk) → void

::: {.features}
inherited
:::

Adds chunked data to this sink.

[addSlice](stringconversionsink/addslice)([String](../dart-core/string-class)
chunk, [int](../dart-core/int-class) start,
[int](../dart-core/int-class) end, [bool](../dart-core/bool-class)
isLast) → void

Adds the next `chunk` to `this`.

[asStringSink](stringconversionsink/asstringsink)() →
[ClosableStringSink](closablestringsink-class)

Returns `this` as a [ClosableStringSink](closablestringsink-class).

[asUtf8Sink](stringconversionsink/asutf8sink)([bool](../dart-core/bool-class)
allowMalformed) → [ByteConversionSink](byteconversionsink-class)

Returns `this` as a sink that accepts UTF-8 input.

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
<https://api.dart.dev/stable/2.18.5/dart-convert/StringConversionSink-class.html>
:::
