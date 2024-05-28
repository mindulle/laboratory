[dart:convert](../dart-convert/dart-convert-library){._links-link}

Utf8Codec class
===============

A [Utf8Codec](utf8codec-class) encodes strings to utf-8 code units
(bytes) and decodes UTF-8 code units to strings.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Codec](codec-class)\<[String](../dart-core/string-class),
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   [Encoding](encoding-class)
    -   Utf8Codec

Constructors
------------

[Utf8Codec](utf8codec/utf8codec)({[bool](../dart-core/bool-class)
allowMalformed = false})

::: {.constructor-modifier .features}
const
:::

Instantiates a new [Utf8Codec](utf8codec-class).

Properties {#instance-properties}
----------

[decoder](utf8codec/decoder) → [Utf8Decoder](utf8decoder-class)

::: {.features}
read-only, override
:::

Returns the decoder of `this`, converting from `List<int>` to `String`.

[encoder](utf8codec/encoder) → [Utf8Encoder](utf8encoder-class)

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

[name](utf8codec/name) → [String](../dart-core/string-class)

::: {.features}
read-only, override
:::

The name of this codec is \"utf-8\".

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[decode](utf8codec/decode)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
codeUnits, {[bool](../dart-core/bool-class)? allowMalformed}) →
[String](../dart-core/string-class)

::: {.features}
override
:::

Decodes the UTF-8 `codeUnits` (a list of unsigned 8-bit integers) to the
corresponding string.

[decodeStream](encoding/decodestream)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
byteStream) →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

[encode](codec/encode)([String](../dart-core/string-class) input) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>

::: {.features}
inherited
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
<https://api.dart.dev/stable/2.18.5/dart-convert/Utf8Codec-class.html>
:::
