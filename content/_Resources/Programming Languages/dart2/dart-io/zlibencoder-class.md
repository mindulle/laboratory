[dart:io](../dart-io/dart-io-library){._links-link}

ZLibEncoder class
=================

The [ZLibEncoder](zlibencoder-class) encoder is used by
[ZLibCodec](zlibcodec-class) and [GZipCodec](gzipcodec-class) to
compress data.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   [Converter](../dart-convert/converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   ZLibEncoder

Constructors
------------

[ZLibEncoder](zlibencoder/zlibencoder)({[bool](../dart-core/bool-class)
gzip = false, [int](../dart-core/int-class) level =
ZLibOption.defaultLevel, [int](../dart-core/int-class) windowBits =
ZLibOption.defaultWindowBits, [int](../dart-core/int-class) memLevel =
ZLibOption.defaultMemLevel, [int](../dart-core/int-class) strategy =
ZLibOption.strategyDefault,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?
dictionary, [bool](../dart-core/bool-class) raw = false})

Properties {#instance-properties}
----------

[dictionary](zlibencoder/dictionary) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?

::: {.features}
final
:::

Initial compression dictionary.

[gzip](zlibencoder/gzip) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

When true, `GZip` frames will be added to the compressed data.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[level](zlibencoder/level) → [int](../dart-core/int-class)

::: {.features}
final
:::

The compression-[level](zlibencoder/level) can be set in the range of
`-1..9`, with `6` being the default compression level. Levels above `6`
will have higher compression rates at the cost of more CPU and memory
usage. Levels below `6` will use less CPU and memory at the cost of
lower compression rates.

[memLevel](zlibencoder/memlevel) → [int](../dart-core/int-class)

::: {.features}
final
:::

Specifies how much memory should be allocated for the internal
compression state. `1` uses minimum memory but is slow and reduces
compression ratio; `9` uses maximum memory for optimal speed. The
default value is `8`.

[raw](zlibencoder/raw) → [bool](../dart-core/bool-class)

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

[strategy](zlibencoder/strategy) → [int](../dart-core/int-class)

::: {.features}
final
:::

Tunes the compression algorithm. Use the value
[ZLibOption.strategyDefault](zliboption/strategydefault-constant) for
normal data,
[ZLibOption.strategyFiltered](zliboption/strategyfiltered-constant) for
data produced by a filter (or predictor),
[ZLibOption.strategyHuffmanOnly](zliboption/strategyhuffmanonly-constant)
to force Huffman encoding only (no string match), or
[ZLibOption.strategyRle](zliboption/strategyrle-constant) to limit match
distances to one (run-length encoding).

[windowBits](zlibencoder/windowbits) → [int](../dart-core/int-class)

::: {.features}
final
:::

Base two logarithm of the window size (the size of the history buffer).
It should be in the range `8..15`. Larger values result in better
compression at the expense of memory usage. The default value is `15`

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

[convert](zlibencoder/convert)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
bytes) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>

::: {.features}
override
:::

Convert a list of bytes using the options given to the ZLibEncoder
constructor.

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

[startChunkedConversion](zlibencoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
sink) → [ByteConversionSink](../dart-convert/byteconversionsink-class)

::: {.features}
override
:::

Start a chunked conversion using the options given to the
[ZLibEncoder](zlibencoder-class) constructor.

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
<https://api.dart.dev/stable/2.18.5/dart-io/ZLibEncoder-class.html>
:::
