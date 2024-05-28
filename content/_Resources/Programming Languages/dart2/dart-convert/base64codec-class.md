[dart:convert](../dart-convert/dart-convert-library){._links-link}

Base64Codec class
=================

A [base64](https://tools.ietf.org/html/rfc4648) encoder and decoder.

A [Base64Codec](base64codec-class) allows base64 encoding bytes into
ASCII strings and decoding valid encodings back to bytes.

This implementation only handles the simplest RFC 4648 base64 and
base64url encodings. It does not allow invalid characters when decoding
and it requires, and generates, padding so that the input is always a
multiple of four characters.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Codec](codec-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
        [String](../dart-core/string-class)\>
    -   Base64Codec

Constructors
------------

[Base64Codec](base64codec/base64codec)()

::: {.constructor-modifier .features}
const
:::

[Base64Codec.urlSafe](base64codec/base64codec.urlsafe)()

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[decoder](base64codec/decoder) → [Base64Decoder](base64decoder-class)

::: {.features}
read-only, override
:::

Returns the decoder of `this`, converting from `T` to `S`.

[encoder](base64codec/encoder) → [Base64Encoder](base64encoder-class)

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
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

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

[decode](base64codec/decode)([String](../dart-core/string-class)
encoded) → [Uint8List](../dart-typed_data/uint8list-class)

::: {.features}
override
:::

Decodes `encoded`.

[encode](codec/encode)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
input) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Encodes `input`.

[fuse](codec/fuse)\<R\>([Codec](codec-class)\<[String](../dart-core/string-class),
R\> other) →
[Codec](codec-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
R\>

::: {.features}
inherited
:::

Fuses `this` with `other`.

[normalize](base64codec/normalize)([String](../dart-core/string-class)
source, \[[int](../dart-core/int-class) start = 0,
[int](../dart-core/int-class)? end\]) →
[String](../dart-core/string-class)

Validates and normalizes the base64 encoded data in `source`.

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
<https://api.dart.dev/stable/2.18.5/dart-convert/Base64Codec-class.html>
:::
