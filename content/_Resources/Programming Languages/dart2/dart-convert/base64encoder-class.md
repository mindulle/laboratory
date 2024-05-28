[dart:convert](../dart-convert/dart-convert-library){._links-link}

Base64Encoder class
===================

Base64 and base64url encoding converter.

Encodes lists of bytes using base64 or base64url encoding.

The results are ASCII strings using a restricted alphabet.

Example:

``` {.language-dart data-language="dart"}
final base64Encoder = base64.encoder;
const sample = 'Dart is open source';
final encodedSample = base64Encoder.convert(sample.codeUnits);
print(encodedSample); // RGFydCBpcyBvcGVuIHNvdXJjZQ==
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [String](../dart-core/string-class)\>
    -   [Converter](converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [String](../dart-core/string-class)\>
    -   Base64Encoder

Constructors
------------

[Base64Encoder](base64encoder/base64encoder)()

::: {.constructor-modifier .features}
const
:::

[Base64Encoder.urlSafe](base64encoder/base64encoder.urlsafe)()

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

[bind](converter/bind)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
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

[convert](base64encoder/convert)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
input) → [String](../dart-core/string-class)

::: {.features}
override
:::

Converts `input` and returns the result of the conversion.

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

[startChunkedConversion](base64encoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[String](../dart-core/string-class)\>
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
<https://api.dart.dev/stable/2.18.5/dart-convert/Base64Encoder-class.html>
:::
