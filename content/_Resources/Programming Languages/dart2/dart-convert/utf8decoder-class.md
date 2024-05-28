[dart:convert](../dart-convert/dart-convert-library){._links-link}

Utf8Decoder class
=================

This class converts UTF-8 code units (lists of unsigned 8-bit integers)
to a string.

Example:

``` {.language-dart data-language="dart"}
final utf8Decoder = utf8.decoder;
const encodedBytes = [
  195, 142, 195, 177, 197, 163, 195, 169, 114, 195, 177, 195, 165, 197,
  163, 195, 174, 195, 182, 195, 177, 195, 165, 196, 188, 195, 174, 197,
  190, 195, 165, 197, 163, 195, 174, 225, 187, 157, 195, 177];

final decodedBytes = utf8Decoder.convert(encodedBytes);
print(decodedBytes); // Îñţérñåţîöñåļîžåţîờñ
```

Throws a [FormatException](../dart-core/formatexception-class) if the
encoded input contains invalid UTF-8 byte sequences and `allowMalformed`
is `false` (the default).

If `allowMalformed` is `true`, invalid byte sequences are converted into
one or more Unicode replacement characters, U+FFFD (\'�\').

Example with `allowMalformed` set to true:

``` {.language-dart data-language="dart"}
const utf8Decoder = Utf8Decoder(allowMalformed: true);
const encodedBytes = [0xFF];
final decodedBytes = utf8Decoder.convert(encodedBytes);
print(decodedBytes); // �
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [String](../dart-core/string-class)\>
    -   [Converter](converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [String](../dart-core/string-class)\>
    -   Utf8Decoder

Constructors
------------

[Utf8Decoder](utf8decoder/utf8decoder)({[bool](../dart-core/bool-class)
allowMalformed = false})

::: {.constructor-modifier .features}
const
:::

Instantiates a new [Utf8Decoder](utf8decoder-class).

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

[bind](utf8decoder/bind)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
stream) →
[Stream](../dart-async/stream-class)\<[String](../dart-core/string-class)\>

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

[convert](utf8decoder/convert)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
codeUnits, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) →
[String](../dart-core/string-class)

::: {.features}
override
:::

Converts the UTF-8 `codeUnits` (a list of unsigned 8-bit integers) to
the corresponding string.

[fuse](utf8decoder/fuse)\<T\>([Converter](converter-class)\<[String](../dart-core/string-class),
T\> next) →
[Converter](converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
T\>

::: {.features}
override
:::

Fuses `this` with `other`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[startChunkedConversion](utf8decoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[String](../dart-core/string-class)\>
sink) → [ByteConversionSink](byteconversionsink-class)

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
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Decoder-class.html>
:::
