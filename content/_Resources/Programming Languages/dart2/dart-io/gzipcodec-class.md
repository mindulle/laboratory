[dart:io](../dart-io/dart-io-library){._links-link}

GZipCodec class
===============

The [GZipCodec](gzipcodec-class) encodes raw bytes to GZip compressed
bytes and decodes GZip compressed bytes to raw bytes.

The difference between [ZLibCodec](zlibcodec-class) and
[GZipCodec](gzipcodec-class) is that the [GZipCodec](gzipcodec-class)
wraps the `ZLib` compressed bytes in `GZip` frames.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Codec](../dart-convert/codec-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   GZipCodec

Constructors
------------

[GZipCodec](gzipcodec/gzipcodec)({[int](../dart-core/int-class) level =
ZLibOption.defaultLevel, [int](../dart-core/int-class) windowBits =
ZLibOption.defaultWindowBits, [int](../dart-core/int-class) memLevel =
ZLibOption.defaultMemLevel, [int](../dart-core/int-class) strategy =
ZLibOption.strategyDefault,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?
dictionary, [bool](../dart-core/bool-class) raw = false,
[bool](../dart-core/bool-class) gzip = true})

Properties {#instance-properties}
----------

[decoder](gzipcodec/decoder) → [ZLibDecoder](zlibdecoder-class)

::: {.features}
read-only, override
:::

Get a [ZLibDecoder](zlibdecoder-class) for decoding `GZip` compressed
data.

[dictionary](gzipcodec/dictionary) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>?

::: {.features}
final
:::

Initial compression dictionary.

[encoder](gzipcodec/encoder) → [ZLibEncoder](zlibencoder-class)

::: {.features}
read-only, override
:::

Get a [ZLibEncoder](zlibencoder-class) for encoding to `GZip` compressed
data.

[gzip](gzipcodec/gzip) → [bool](../dart-core/bool-class)

::: {.features}
final
:::

When true, `GZip` frames will be added to the compressed data.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[inverted](../dart-convert/codec/inverted) →
[Codec](../dart-convert/codec-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
read-only, inherited
:::

Inverts `this`.

[level](gzipcodec/level) → [int](../dart-core/int-class)

::: {.features}
final
:::

The compression-[level](gzipcodec/level) can be set in the range of
`-1..9`, with `6` being the default compression level. Levels above `6`
will have higher compression rates at the cost of more CPU and memory
usage. Levels below `6` will use less CPU and memory at the cost of
lower compression rates.

[memLevel](gzipcodec/memlevel) → [int](../dart-core/int-class)

::: {.features}
final
:::

Specifies how much memory should be allocated for the internal
compression state. `1` uses minimum memory but is slow and reduces
compression ratio; `9` uses maximum memory for optimal speed. The
default value is `8`.

[raw](gzipcodec/raw) → [bool](../dart-core/bool-class)

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

[strategy](gzipcodec/strategy) → [int](../dart-core/int-class)

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

[windowBits](gzipcodec/windowbits) → [int](../dart-core/int-class)

::: {.features}
final
:::

Base two logarithm of the window size (the size of the history buffer).
It should be in the range `8..15`. Larger values result in better
compression at the expense of memory usage. The default value is `15`

Methods {#instance-methods}
-------

[decode](../dart-convert/codec/decode)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
encoded) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>

::: {.features}
inherited
:::

Decodes `encoded` data.

[encode](../dart-convert/codec/encode)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
input) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>

::: {.features}
inherited
:::

Encodes `input`.

[fuse](../dart-convert/codec/fuse)\<R\>([Codec](../dart-convert/codec-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
R\> other) →
[Codec](../dart-convert/codec-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
R\>

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
<https://api.dart.dev/stable/2.18.5/dart-io/GZipCodec-class.html>
:::
