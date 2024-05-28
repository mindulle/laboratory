[dart:convert](../dart-convert/dart-convert-library){._links-link}

Codec\<S, T\> class
===================

A [Codec](codec-class) encodes and (if supported) decodes data.

Codecs can be fused. For example fusing [json](json-constant) and
[utf8](utf8-constant) produces an encoder that can convert Json objects
directly to bytes, or can decode bytes directly to json objects.

Fused codecs generally attempt to optimize the operations and can be
faster than executing each step of an encoding separately.

Implementers

:   -   [Base64Codec](base64codec-class)
    -   [Encoding](encoding-class)
    -   [GZipCodec](../dart-io/gzipcodec-class)
    -   [JsonCodec](jsoncodec-class)
    -   [ZLibCodec](../dart-io/zlibcodec-class)

Constructors
------------

[Codec](codec/codec)()

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[decoder](codec/decoder) → [Converter](converter-class)\<T, S\>

::: {.features}
read-only
:::

Returns the decoder of `this`, converting from `T` to `S`.

[encoder](codec/encoder) → [Converter](converter-class)\<S, T\>

::: {.features}
read-only
:::

Returns the encoder from `S` to `T`.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[inverted](codec/inverted) → [Codec](codec-class)\<T, S\>

::: {.features}
read-only
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

[decode](codec/decode)(T encoded) → S

Decodes `encoded` data.

[encode](codec/encode)(S input) → T

Encodes `input`.

[fuse](codec/fuse)\<R\>([Codec](codec-class)\<T, R\> other) →
[Codec](codec-class)\<S, R\>

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
<https://api.dart.dev/stable/2.18.5/dart-convert/Codec-class.html>
:::
