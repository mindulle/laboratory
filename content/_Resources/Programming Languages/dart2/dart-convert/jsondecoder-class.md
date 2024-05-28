[dart:convert](../dart-convert/dart-convert-library){._links-link}

JsonDecoder class
=================

This class parses JSON strings and builds the corresponding objects.

A JSON input must be the JSON encoding of a single JSON value, which can
be a list or map containing other values.

Throws [FormatException](../dart-core/formatexception-class) if the
input is not valid JSON text.

Example:

``` {.language-dart data-language="dart"}
const JsonDecoder decoder = JsonDecoder();

const String jsonString = '''
  {
    "data": [{"text": "foo", "value": 1 },
             {"text": "bar", "value": 2 }],
    "text": "Dart"
  }
''';

final Map<String, dynamic> object = decoder.convert(jsonString);

final item = object['data'][0];
print(item['text']); // foo
print(item['value']); // 1

print(object['text']); // Dart
```

When used as a
[StreamTransformer](../dart-async/streamtransformer-class), the input
stream may emit multiple strings. The concatenation of all of these
strings must be a valid JSON encoding of a single JSON value.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [StreamTransformerBase](../dart-async/streamtransformerbase-class)\<[String](../dart-core/string-class),
        [Object](../dart-core/object-class)?\>
    -   [Converter](converter-class)\<[String](../dart-core/string-class),
        [Object](../dart-core/object-class)?\>
    -   JsonDecoder

Constructors
------------

[JsonDecoder](jsondecoder/jsondecoder)(\[[Object](../dart-core/object-class)?
reviver([Object](../dart-core/object-class)? key,
[Object](../dart-core/object-class)? value)?\])

::: {.constructor-modifier .features}
const
:::

Constructs a new JsonDecoder.

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

[bind](jsondecoder/bind)([Stream](../dart-async/stream-class)\<[String](../dart-core/string-class)\>
stream) →
[Stream](../dart-async/stream-class)\<[Object](../dart-core/object-class)?\>

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

[convert](jsondecoder/convert)([String](../dart-core/string-class)
input) → dynamic

::: {.features}
override
:::

Converts the given JSON-string `input` to its corresponding object.

[fuse](converter/fuse)\<TT\>([Converter](converter-class)\<[Object](../dart-core/object-class)?,
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

[startChunkedConversion](jsondecoder/startchunkedconversion)([Sink](../dart-core/sink-class)\<[Object](../dart-core/object-class)?\>
sink) → [StringConversionSink](stringconversionsink-class)

::: {.features}
override
:::

Starts a conversion from a chunked JSON string to its corresponding
object.

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
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonDecoder-class.html>
:::
