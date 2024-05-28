[dart:convert](../dart-convert/dart-convert-library){._links-link}

Latin1Codec class
=================

A [Latin1Codec](latin1codec-class) encodes strings to ISO Latin-1 (aka
ISO-8859-1) bytes and decodes Latin-1 bytes to strings.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Codec](codec-class)\<[String](../dart-core/string-class),
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   [Encoding](encoding-class)
    -   Latin1Codec

Constructors
------------

[Latin1Codec](latin1codec/latin1codec)({[bool](../dart-core/bool-class)
allowInvalid = false})

::: {.constructor-modifier .features}
const
:::

Instantiates a new [Latin1Codec](latin1codec-class).

Properties {#instance-properties}
----------

[decoder](latin1codec/decoder) → [Latin1Decoder](latin1decoder-class)

::: {.features}
read-only, override
:::

Returns the decoder of `this`, converting from `List<int>` to `String`.

[encoder](latin1codec/encoder) → [Latin1Encoder](latin1encoder-class)

::: {.features}
read-only, override
:::

Returns the encoder from `String` to `List<int>`.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[inverted](codec/inverted) →
[Codec](codec-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
[String](../dart-core/string-class)\>

::: {.features}
read-only, inherited
:::

Inverts `this`.

[name](latin1codec/name) → [String](../dart-core/string-class)

::: {.features}
read-only, override
:::

The name of this codec, \"iso-8859-1\".

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[decode](latin1codec/decode)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
bytes, {[bool](../dart-core/bool-class)? allowInvalid}) →
[String](../dart-core/string-class)

::: {.features}
override
:::

Decodes the Latin-1 `bytes` (a list of unsigned 8-bit integers) to the
corresponding string.

[decodeStream](encoding/decodestream)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
byteStream) →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

[encode](latin1codec/encode)([String](../dart-core/string-class) source)
→ [Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
override
:::

Encodes `input`.

[fuse](codec/fuse)\<R\>([Codec](codec-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
R\> other) → [Codec](codec-class)\<[String](../dart-core/string-class),
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
<https://api.dart.dev/stable/2.18.5/dart-convert/Latin1Codec-class.html>
:::
