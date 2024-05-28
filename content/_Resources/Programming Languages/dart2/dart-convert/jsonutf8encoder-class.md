[dart:convert](../dart-convert/dart-convert-library){._links-link}

JsonUtf8Encoder class
=====================

Encoder that encodes a single object as a UTF-8 encoded JSON string.

This encoder works equivalently to first converting the object to a JSON
string, and then UTF-8 encoding the string, but without creating an
intermediate string.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[Object](../dart-core/object-class)?,
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   [Converter](converter-class)\<[Object](../dart-core/object-class)?,
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   JsonUtf8Encoder

Constructors
------------

[JsonUtf8Encoder](jsonutf8encoder/jsonutf8encoder)(\[[String](../dart-core/string-class)? indent, dynamic toEncodable(dynamic object)?, [int](../dart-core/int-class)? bufferSize\])
:   Create converter.

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

[bind](jsonutf8encoder/bind)([Stream](../dart-async/stream-class)\<[Object](../dart-core/object-class)?\>
stream) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
override
:::

Transforms the provided `stream`.

[cast](converter/cast)\<RS, RT\>() → [Converter](converter-class)\<RS,
RT\>

::: {.features}
inherited
:::

Provides a `Converter<RS, RT>` view of this stream transformer.

[convert](jsonutf8encoder/convert)([Object](../dart-core/object-class)?
object) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>

::: {.features}
override
:::

Convert `object` into UTF-8 encoded JSON.

[fuse](converter/fuse)\<TT\>([Converter](converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
TT\> other) →
[Converter](converter-class)\<[Object](../dart-core/object-class)?, TT\>

::: {.features}
inherited
:::

Fuses `this` with `other`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[startChunkedConversion](jsonutf8encoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
sink) →
[ChunkedConversionSink](chunkedconversionsink-class)\<[Object](../dart-core/object-class)?\>

::: {.features}
override
:::

Start a chunked conversion.

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

Constants
---------

[DEFAULT\_BUFFER\_SIZE](jsonutf8encoder/default_buffer_size-constant){.deprecated} → const [int](../dart-core/int-class)

:   <div>

    `_defaultBufferSize`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonUtf8Encoder-class.html>
:::
