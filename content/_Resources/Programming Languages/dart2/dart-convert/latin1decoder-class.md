[dart:convert](../dart-convert/dart-convert-library){._links-link}

Latin1Decoder class
===================

This class converts Latin-1 bytes (lists of unsigned 8-bit integers) to
a string.

Example:

``` {.language-dart data-language="dart"}
final latin1Decoder = latin1.decoder;

const encodedBytes = [224, 225, 226, 227, 228, 229];
final decoded = latin1Decoder.convert(encodedBytes);
print(decoded); // àáâãäå

// Hexadecimal values as source
const hexBytes = [0xe0, 0xe1, 0xe2, 0xe3, 0xe4, 0xe5];
final decodedHexBytes = latin1Decoder.convert(hexBytes);
print(decodedHexBytes); // àáâãäå
```

Throws a [FormatException](../dart-core/formatexception-class) if the
encoded input contains values that are not in the range 0 .. 255 and
`allowInvalid` is false ( the default ).

If `allowInvalid` is true, invalid bytes are converted to Unicode
Replacement character U+FFFD (�).

Example with `allowInvalid` set to true:

``` {.language-dart data-language="dart"}
const latin1Decoder = Latin1Decoder(allowInvalid: true);
const encodedBytes = [300];
final decoded = latin1Decoder.convert(encodedBytes);
print(decoded); // �
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [String](../dart-core/string-class)\>
    -   [Converter](converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [String](../dart-core/string-class)\>
    -   Latin1Decoder

Constructors
------------

[Latin1Decoder](latin1decoder/latin1decoder)({[bool](../dart-core/bool-class)
allowInvalid = false})

::: {.constructor-modifier .features}
const
:::

Instantiates a new [Latin1Decoder](latin1decoder-class).

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

[bind](latin1decoder/bind)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
stream) →
[Stream](../dart-async/stream-class)\<[String](../dart-core/string-class)\>

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

[convert](latin1decoder/convert)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
bytes, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

Converts the `bytes` (a list of unsigned 7- or 8-bit integers) to the
corresponding string.

[fuse](converter/fuse)\<TT\>([Converter](converter-class)\<[String](../dart-core/string-class),
TT\> other) →
[Converter](converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
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

[startChunkedConversion](latin1decoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[String](../dart-core/string-class)\>
sink) → [ByteConversionSink](byteconversionsink-class)

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
<https://api.dart.dev/stable/2.18.5/dart-convert/Latin1Decoder-class.html>
:::
