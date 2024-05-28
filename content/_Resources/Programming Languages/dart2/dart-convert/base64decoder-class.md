[dart:convert](../dart-convert/dart-convert-library){._links-link}

Base64Decoder class
===================

Decoder for base64 encoded data.

This decoder accepts both base64 and base64url (\"url-safe\") encodings.

The encoding is required to be properly padded.

Throws a [FormatException](../dart-core/formatexception-class) if the
input is not valid base64 data.

Example:

``` {.language-dart data-language="dart"}
final base64Decoder = base64.decoder;
const base64Bytes = 'RGFydCBpcyBvcGVuIHNvdXJjZQ==';
final decodedBytes = base64Decoder.convert(base64Bytes);
// decodedBytes: [68, 97, 114, 116, 32, 105, 115, 32, 111, 112, 101, 110,
// 32, 115, 111, 117, 114, 99, 101]

// Print as string using UTF-8 decoder
print(utf8.decode(decodedBytes)); // Dart is open source
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[String](../dart-core/string-class),
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   [Converter](converter-class)\<[String](../dart-core/string-class),
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   Base64Decoder

Constructors
------------

[Base64Decoder](base64decoder/base64decoder)()

::: {.constructor-modifier .features}
const
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

[bind](converter/bind)([Stream](../dart-async/stream-class)\<[String](../dart-core/string-class)\>
stream) →
[Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

::: {.features}
inherited
:::

Transforms the provided `stream`.

[cast](converter/cast)\<RS, RT\>() → [Converter](converter-class)\<RS,
RT\>

::: {.features}
inherited
:::

Provides a `Converter<RS, RT>` view of this stream transformer.

[convert](base64decoder/convert)([String](../dart-core/string-class)
input, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) →
[Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
override
:::

Decodes the characters of `input` from `start` to `end` as base64.

[fuse](converter/fuse)\<TT\>([Converter](converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
TT\> other) →
[Converter](converter-class)\<[String](../dart-core/string-class), TT\>

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

[startChunkedConversion](base64decoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
sink) → [StringConversionSink](stringconversionsink-class)

::: {.features}
override
:::

Starts a chunked conversion.

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
<https://api.dart.dev/stable/2.18.5/dart-convert/Base64Decoder-class.html>
:::
