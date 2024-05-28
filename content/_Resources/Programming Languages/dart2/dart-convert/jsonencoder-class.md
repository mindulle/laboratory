[dart:convert](../dart-convert/dart-convert-library){._links-link}

JsonEncoder class
=================

This class converts JSON objects to strings.

Example:

``` {.language-dart data-language="dart"}
const JsonEncoder encoder = JsonEncoder();
const data = {'text': 'foo', 'value': '2'};

final String jsonString = encoder.convert(data);
print(jsonString); // {"text":"foo","value":"2"}
```

Example of pretty-printed output:

``` {.language-dart data-language="dart"}
const JsonEncoder encoder = JsonEncoder.withIndent('  ');

const data = {'text': 'foo', 'value': '2'};
final String jsonString = encoder.convert(data);
print(jsonString);
// {
//   "text": "foo",
//   "value": "2"
// }
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[Object](../dart-core/object-class)?,
        [String](../dart-core/string-class)\>
    -   [Converter](converter-class)\<[Object](../dart-core/object-class)?,
        [String](../dart-core/string-class)\>
    -   JsonEncoder

Constructors
------------

[JsonEncoder](jsonencoder/jsonencoder)(\[[Object](../dart-core/object-class)?
toEncodable(dynamic object)?\])

::: {.constructor-modifier .features}
const
:::

Creates a JSON encoder.

[JsonEncoder.withIndent](jsonencoder/jsonencoder.withindent)([String](../dart-core/string-class)?
indent, \[[Object](../dart-core/object-class)? toEncodable(dynamic
object)?\])

::: {.constructor-modifier .features}
const
:::

Creates a JSON encoder that creates multi-line JSON.

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[indent](jsonencoder/indent) → [String](../dart-core/string-class)?

::: {.features}
final
:::

The string used for indention.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[bind](jsonencoder/bind)([Stream](../dart-async/stream-class)\<[Object](../dart-core/object-class)?\>
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

[convert](jsonencoder/convert)([Object](../dart-core/object-class)?
object) → [String](../dart-core/string-class)

::: {.features}
override
:::

Converts `object` to a JSON [String](../dart-core/string-class).

[fuse](jsonencoder/fuse)\<T\>([Converter](converter-class)\<[String](../dart-core/string-class),
T\> other) →
[Converter](converter-class)\<[Object](../dart-core/object-class)?, T\>

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

[startChunkedConversion](jsonencoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[String](../dart-core/string-class)\>
sink) →
[ChunkedConversionSink](chunkedconversionsink-class)\<[Object](../dart-core/object-class)?\>

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
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonEncoder-class.html>
:::
