[dart:convert](../dart-convert/dart-convert-library){._links-link}

AsciiDecoder class
==================

Converts ASCII bytes to string.

Example:

``` {.language-dart data-language="dart"}
const asciiDecoder = AsciiDecoder();
final asciiValues = [68, 97, 114, 116];
final result = asciiDecoder.convert(asciiValues);
print(result); // Dart
```

Throws a [FormatException](../dart-core/formatexception-class) if
`bytes` contains values that are not in the range 0 .. 127, and
`allowInvalid` is `false` (the default).

If `allowInvalid` is `true`, any byte outside the range 0..127 is
replaced by the Unicode replacement character, U+FFFD (\'�\').

Example with `allowInvalid` set to true:

``` {.language-dart data-language="dart"}
const asciiDecoder = AsciiDecoder(allowInvalid: true);
final asciiValues = [68, 97, 114, 116, 20, 0xFF];
final result = asciiDecoder.convert(asciiValues);
print(result); // Dart �
print(result.codeUnits.last.toRadixString(16)); // fffd
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [String](../dart-core/string-class)\>
    -   [Converter](converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [String](../dart-core/string-class)\>
    -   AsciiDecoder

Constructors
------------

[AsciiDecoder](asciidecoder/asciidecoder)({[bool](../dart-core/bool-class)
allowInvalid = false})

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

[bind](asciidecoder/bind)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
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

[convert](asciidecoder/convert)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
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

[startChunkedConversion](asciidecoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[String](../dart-core/string-class)\>
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
<https://api.dart.dev/stable/2.18.5/dart-convert/AsciiDecoder-class.html>
:::
