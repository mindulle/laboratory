[dart:convert](../dart-convert/dart-convert-library){._links-link}

Utf8Encoder class
=================

This class converts strings to their UTF-8 code units (a list of
unsigned 8-bit integers).

Example:

``` {.language-dart data-language="dart"}
final utf8Encoder = utf8.encoder;
const sample = 'Îñţérñåţîöñåļîžåţîờñ';
final encodedSample = utf8Encoder.convert(sample);
print(encodedSample);
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[String](../dart-core/string-class),
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   [Converter](converter-class)\<[String](../dart-core/string-class),
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   Utf8Encoder

Constructors
------------

[Utf8Encoder](utf8encoder/utf8encoder)()

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

[bind](utf8encoder/bind)([Stream](../dart-async/stream-class)\<[String](../dart-core/string-class)\>
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

[convert](utf8encoder/convert)([String](../dart-core/string-class)
string, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) →
[Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
override
:::

Converts `string` to its UTF-8 code units (a list of unsigned 8-bit
integers).

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

[startChunkedConversion](utf8encoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
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
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Encoder-class.html>
:::
