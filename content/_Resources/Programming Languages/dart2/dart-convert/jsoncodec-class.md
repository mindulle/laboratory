[dart:convert](../dart-convert/dart-convert-library){._links-link}

JsonCodec class
===============

A [JsonCodec](jsoncodec-class) encodes JSON objects to strings and
decodes strings to JSON objects.

Examples:

``` {.language-dart data-language="dart"}
var encoded = json.encode([1, 2, { "a": null }]);
var decoded = json.decode('["foo", { "bar": 499 }]');
```

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Codec](codec-class)\<[Object](../dart-core/object-class)?,
        [String](../dart-core/string-class)\>
    -   JsonCodec

Constructors
------------

[JsonCodec](jsoncodec/jsoncodec)({[Object](../dart-core/object-class)?
reviver([Object](../dart-core/object-class)? key,
[Object](../dart-core/object-class)? value)?,
[Object](../dart-core/object-class)? toEncodable(dynamic object)?})

::: {.constructor-modifier .features}
const
:::

Creates a `JsonCodec` with the given reviver and encoding function.

[JsonCodec.withReviver](jsoncodec/jsoncodec.withreviver)(dynamic
reviver([Object](../dart-core/object-class)? key,
[Object](../dart-core/object-class)? value))

Creates a `JsonCodec` with the given reviver.

Properties {#instance-properties}
----------

[decoder](jsoncodec/decoder) → [JsonDecoder](jsondecoder-class)

::: {.features}
read-only, override
:::

Returns the decoder of `this`, converting from `T` to `S`.

[encoder](jsoncodec/encoder) → [JsonEncoder](jsonencoder-class)

::: {.features}
read-only, override
:::

Returns the encoder from `S` to `T`.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[inverted](codec/inverted) →
[Codec](codec-class)\<[String](../dart-core/string-class),
[Object](../dart-core/object-class)?\>

::: {.features}
read-only, inherited
:::

Inverts `this`.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[decode](jsoncodec/decode)([String](../dart-core/string-class) source,
{[Object](../dart-core/object-class)?
reviver([Object](../dart-core/object-class)? key,
[Object](../dart-core/object-class)? value)?}) → dynamic

::: {.features}
override
:::

Parses the string and returns the resulting Json object.

[encode](jsoncodec/encode)([Object](../dart-core/object-class)? value,
{[Object](../dart-core/object-class)? toEncodable(dynamic object)?}) →
[String](../dart-core/string-class)

::: {.features}
override
:::

Converts `value` to a JSON string.

[fuse](codec/fuse)\<R\>([Codec](codec-class)\<[String](../dart-core/string-class),
R\> other) → [Codec](codec-class)\<[Object](../dart-core/object-class)?,
R\>

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
<https://api.dart.dev/stable/2.18.5/dart-convert/JsonCodec-class.html>
:::
