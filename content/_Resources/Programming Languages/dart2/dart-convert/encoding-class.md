[dart:convert](../dart-convert/dart-convert-library){._links-link}

Encoding class
==============

Open-ended Encoding enum.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Codec](codec-class)\<[String](../dart-core/string-class),
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   Encoding

Implementers

:   -   [AsciiCodec](asciicodec-class)
    -   [Latin1Codec](latin1codec-class)
    -   [SystemEncoding](../dart-io/systemencoding-class)
    -   [Utf8Codec](utf8codec-class)

Constructors
------------

[Encoding](encoding/encoding)()

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[decoder](encoding/decoder) →
[Converter](converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
[String](../dart-core/string-class)\>

::: {.features}
read-only, override
:::

Returns the decoder of `this`, converting from `List<int>` to `String`.

[encoder](encoding/encoder) →
[Converter](converter-class)\<[String](../dart-core/string-class),
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>

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

[name](encoding/name) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

Name of the encoding.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[decode](codec/decode)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
encoded) → [String](../dart-core/string-class)

::: {.features}
inherited
:::

Decodes `encoded` data.

[decodeStream](encoding/decodestream)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
byteStream) →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

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

Static Methods
--------------

[getByName](encoding/getbyname)([String](../dart-core/string-class)? name) → [Encoding](encoding-class)?
:   Returns an [Encoding](encoding-class) for a named character set.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-convert/Encoding-class.html>
:::
