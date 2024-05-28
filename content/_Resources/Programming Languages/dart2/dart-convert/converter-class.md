[dart:convert](../dart-convert/dart-convert-library){._links-link}

Converter\<S, T\> class
=======================

A [Converter](converter-class) converts data from one representation
into another.

It is recommended that implementations of `Converter` extend this class,
to inherit any further methods that may be added to the class.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<S,
        T\>
    -   Converter

Implementers

:   -   [AsciiDecoder](asciidecoder-class)
    -   [AsciiEncoder](asciiencoder-class)
    -   [Base64Decoder](base64decoder-class)
    -   [Base64Encoder](base64encoder-class)
    -   [HtmlEscape](htmlescape-class)
    -   [JsonDecoder](jsondecoder-class)
    -   [JsonEncoder](jsonencoder-class)
    -   [JsonUtf8Encoder](jsonutf8encoder-class)
    -   [Latin1Decoder](latin1decoder-class)
    -   [Latin1Encoder](latin1encoder-class)
    -   [Utf8Decoder](utf8decoder-class)
    -   [Utf8Encoder](utf8encoder-class)
    -   [ZLibDecoder](../dart-io/zlibdecoder-class)
    -   [ZLibEncoder](../dart-io/zlibencoder-class)

Constructors
------------

[Converter](converter/converter)()

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

[bind](converter/bind)([Stream](../dart-async/stream-class)\<S\> stream)
→ [Stream](../dart-async/stream-class)\<T\>

::: {.features}
override
:::

Transforms the provided `stream`.

[cast](converter/cast)\<RS, RT\>() → [Converter](converter-class)\<RS,
RT\>

::: {.features}
override
:::

Provides a `Converter<RS, RT>` view of this stream transformer.

[convert](converter/convert)(S input) → T

Converts `input` and returns the result of the conversion.

[fuse](converter/fuse)\<TT\>([Converter](converter-class)\<T, TT\>
other) → [Converter](converter-class)\<S, TT\>

Fuses `this` with `other`.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[startChunkedConversion](converter/startchunkedconversion)([Sink](../dart-core/sink-class)\<T\>
sink) → [Sink](../dart-core/sink-class)\<S\>

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

Static Methods
--------------

[castFrom](converter/castfrom)\<SS, ST, TS,
TT\>([Converter](converter-class)\<SS, ST\> source) →
[Converter](converter-class)\<TS, TT\>

::: {.features}
override
:::

Adapts `source` to be a `Converter<TS, TT>`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Converter-class.html>
:::
