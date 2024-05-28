[dart:convert](../dart-convert/dart-convert-library){._links-link}

AsciiEncoder class
==================

Converts strings of only ASCII characters to bytes.

Example:

``` {.language-dart data-language="dart"}
const asciiEncoder = AsciiEncoder();
const sample = 'Dart';
final asciiValues = asciiEncoder.convert(sample);
print(asciiValues); // [68, 97, 114, 116]
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[String](../dart-core/string-class),
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   [Converter](converter-class)\<[String](../dart-core/string-class),
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   AsciiEncoder

Constructors
------------

[AsciiEncoder](asciiencoder/asciiencoder)()

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

[bind](asciiencoder/bind)([Stream](../dart-async/stream-class)\<[String](../dart-core/string-class)\>
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

[convert](asciiencoder/convert)([String](../dart-core/string-class)
string, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) →
[Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
inherited
:::

Converts the [String](../dart-core/string-class) into a list of its code
units.

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

[startChunkedConversion](asciiencoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
sink) → [StringConversionSink](stringconversionsink-class)

::: {.features}
inherited
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
<https://api.dart.dev/stable/2.18.5/dart-convert/AsciiEncoder-class.html>
:::
