[dart:core](../dart-core/dart-core-library){._links-link}

UriData class
=============

A way to access the structure of a `data:` URI.

Data URIs are non-hierarchical URIs that can contain any binary data.
They are defined by [RFC 2397](https://tools.ietf.org/html/rfc2397).

This class allows parsing the URI text, extracting individual parts of
the URI, as well as building the URI text from structured parts.

Constructors
------------

[UriData.fromBytes](uridata/uridata.frombytes)([List](list-class)\<[int](int-class)\>
bytes, {[String](string-class) mimeType = \"application/octet-stream\",
[Map](map-class)\<[String](string-class), [String](string-class)\>?
parameters, [bool](bool-class) percentEncoded = false})

::: {.constructor-modifier .features}
factory
:::

Creates a `data:` URI containing an encoding of `bytes`.

[UriData.fromString](uridata/uridata.fromstring)([String](string-class)
content, {[String](string-class)? mimeType,
[Encoding](../dart-convert/encoding-class)? encoding,
[Map](map-class)\<[String](string-class), [String](string-class)\>?
parameters, [bool](bool-class) base64 = false})

::: {.constructor-modifier .features}
factory
:::

Creates a `data:` URI containing the `content` string.

[UriData.fromUri](uridata/uridata.fromuri)([Uri](uri-class) uri)

::: {.constructor-modifier .features}
factory
:::

Creates a `DataUri` from a [Uri](uri-class) which must have `data` as
[Uri.scheme](uri/scheme).

Properties {#instance-properties}
----------

[charset](uridata/charset) → [String](string-class)

::: {.features}
read-only
:::

The charset parameter of the media type.

[contentText](uridata/contenttext) → [String](string-class)

::: {.features}
read-only
:::

The content part of the data URI, as its actual representation.

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[isBase64](uridata/isbase64) → [bool](bool-class)

::: {.features}
read-only
:::

Whether the data is Base64 encoded or not.

[mimeType](uridata/mimetype) → [String](string-class)

::: {.features}
read-only
:::

The MIME type of the data URI.

[parameters](uridata/parameters) →
[Map](map-class)\<[String](string-class), [String](string-class)\>

::: {.features}
read-only
:::

A map representing the parameters of the media type.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[uri](uridata/uri) → [Uri](uri-class)

::: {.features}
read-only
:::

The [Uri](uri-class) that this `UriData` is giving access to.

Methods {#instance-methods}
-------

[contentAsBytes](uridata/contentasbytes)() →
[Uint8List](../dart-typed_data/uint8list-class)

The content part of the data URI as bytes.

[contentAsString](uridata/contentasstring)({[Encoding](../dart-convert/encoding-class)?
encoding}) → [String](string-class)

Creates a string from the content of the data URI.

[isCharset](uridata/ischarset)([String](string-class) charset) →
[bool](bool-class)

::: {.features}
\@Since(\"2.17\")
:::

Checks whether the charset parameter of the mime type is `charset`.

[isEncoding](uridata/isencoding)([Encoding](../dart-convert/encoding-class)
encoding) → [bool](bool-class)

::: {.features}
\@Since(\"2.17\")
:::

Whether the charset parameter represents `encoding`.

[isMimeType](uridata/ismimetype)([String](string-class) mimeType) →
[bool](bool-class)

::: {.features}
\@Since(\"2.17\")
:::

Whether the [UriData.mimeType](uridata/mimetype) is equal to `mimeType`.

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](uridata/tostring)() → [String](string-class)

::: {.features}
override
:::

A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[parse](uridata/parse)([String](string-class) uri) → [UriData](uridata-class)
:   Parses a string as a `data` URI.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/UriData-class.html>
:::
