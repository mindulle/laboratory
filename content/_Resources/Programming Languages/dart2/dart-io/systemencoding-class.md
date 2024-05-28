[dart:io](../dart-io/dart-io-library){._links-link}

SystemEncoding class
====================

The system encoding is the current code page on Windows and UTF-8 on
Linux and Mac.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Codec](../dart-convert/codec-class)\<[String](../dart-core/string-class),
        [List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
    -   [Encoding](../dart-convert/encoding-class)
    -   SystemEncoding

Constructors
------------

[SystemEncoding](systemencoding/systemencoding)()

::: {.constructor-modifier .features}
const
:::

Creates a const SystemEncoding.

Properties {#instance-properties}
----------

[decoder](systemencoding/decoder) →
[Converter](../dart-convert/converter-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
[String](../dart-core/string-class)\>

::: {.features}
read-only, override
:::

Returns the decoder of `this`, converting from `List<int>` to `String`.

[encoder](systemencoding/encoder) →
[Converter](../dart-convert/converter-class)\<[String](../dart-core/string-class),
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

[inverted](../dart-convert/codec/inverted) →
[Codec](../dart-convert/codec-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
[String](../dart-core/string-class)\>

::: {.features}
read-only, inherited
:::

Inverts `this`.

[name](systemencoding/name) → [String](../dart-core/string-class)

::: {.features}
read-only, override
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

[decode](systemencoding/decode)([List](../dart-core/list-class)\<[int](../dart-core/int-class)\>
encoded) → [String](../dart-core/string-class)

::: {.features}
override
:::

Decodes `encoded` data.

[decodeStream](../dart-convert/encoding/decodestream)([Stream](../dart-async/stream-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>\>
byteStream) →
[Future](../dart-async/future-class)\<[String](../dart-core/string-class)\>

::: {.features}
inherited
:::

[encode](systemencoding/encode)([String](../dart-core/string-class)
input) →
[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>

::: {.features}
override
:::

Encodes `input`.

[fuse](../dart-convert/codec/fuse)\<R\>([Codec](../dart-convert/codec-class)\<[List](../dart-core/list-class)\<[int](../dart-core/int-class)\>,
R\> other) →
[Codec](../dart-convert/codec-class)\<[String](../dart-core/string-class),
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
<https://api.dart.dev/stable/2.18.5/dart-io/SystemEncoding-class.html>
:::
