[dart:io](../dart-io/dart-io-library){._links-link}

ZLibDecoder class
=================

The [ZLibDecoder](zlibdecoder-class) is used by
[ZLibCodec](zlibcodec-class) and [GZipCodec](gzipcodec-class) to
decompress data.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   [Converter](../dart-convert/converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   ZLibDecoder

Constructors
------------

[ZLibDecoder](zlibdecoder/zlibdecoder)({[int](../dart-core/int-class)
windowBits = ZLibOption.defaultWindowBits,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?
dictionary, [bool](../dart-core/bool-class) raw = false})

Properties {#instance-properties}
----------

[dictionary](zlibdecoder/dictionary) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?

::: {.features}
final
:::

Initial compression dictionary.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[raw](zlibdecoder/raw) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

When true, deflate generates raw data with no zlib header or trailer,
and will not compute an adler32 check value

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[windowBits](zlibdecoder/windowbits) → [int](../dart-core/int-class)

::: {.features}
final
:::

Base two logarithm of the window size (the size of the history buffer).
It should be in the range `8..15`. Larger values result in better
compression at the expense of memory usage. The default value is `15`.

Methods {#instance-methods}
-------

[bind](../dart-convert/converter/bind)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
stream) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Transforms the provided `stream`.

[cast](../dart-convert/converter/cast)\<RS, RT\>() →
[Converter](../dart-convert/converter-class)\<RS, RT\>

::: {.features}
inherited
:::

Provides a `Converter<RS, RT>` view of this stream transformer.

[convert](zlibdecoder/convert)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
bytes) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>

::: {.features}
override
:::

Convert a list of bytes using the options given to the
[ZLibDecoder](zlibdecoder-class) constructor.

[fuse](../dart-convert/converter/fuse)\<TT\>([Converter](../dart-convert/converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
TT\> other) →
[Converter](../dart-convert/converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
TT\>

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

[startChunkedConversion](zlibdecoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
sink) → [ByteConversionSink](../dart-convert/byteconversionsink-class)

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibDecoder-class.html>
:::
