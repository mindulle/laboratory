[dart:io](../dart-io/dart-io-library){._links-link}

ContentType class
=================

A MIME/IANA media type used as the value of the
[HttpHeaders.contentTypeHeader](httpheaders/contenttypeheader-constant)
header.

A [ContentType](contenttype-class) is immutable.

Implemented types

:   -   [HeaderValue](headervalue-class)

Constructors
------------

[ContentType](contenttype/contenttype)([String](../dart-core/string-class)
primaryType, [String](../dart-core/string-class) subType,
{[String](../dart-core/string-class)? charset,
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)?\> parameters = const {}})

::: {.constructor-modifier .features}
factory
:::

Creates a new content type object setting the primary type and sub type.
The charset and additional parameters can also be set using `charset`
and `parameters`. If charset is passed and `parameters` contains charset
as well the passed `charset` will override the value in parameters. Keys
passed in parameters will be converted to lower case. The `charset`
entry, whether passed as `charset` or in `parameters`, will have its
value converted to lower-case.

Properties {#instance-properties}
----------

[charset](contenttype/charset) → [String](../dart-core/string-class)?

::: {.features}
read-only
:::

Gets the character set, if any.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[mimeType](contenttype/mimetype) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

Gets the MIME type and subtype, without any parameters.

[parameters](headervalue/parameters) →
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)?\>

::: {.features}
read-only, inherited
:::

A map of parameters.

[primaryType](contenttype/primarytype) →
[String](../dart-core/string-class)

::: {.features}
read-only
:::

Gets the primary type.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[subType](contenttype/subtype) → [String](../dart-core/string-class)

::: {.features}
read-only
:::

Gets the subtype.

[value](headervalue/value) → [String](../dart-core/string-class)

::: {.features}
read-only, inherited
:::

The value of the header.

Methods {#instance-methods}
-------

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

Static Properties
-----------------

[binary](contenttype/binary) → [ContentType](contenttype-class)

::: {.features}
final
:::

Content type for binary data.

[html](contenttype/html) → [ContentType](contenttype-class)

::: {.features}
final
:::

Content type for HTML using UTF-8 encoding.

[json](contenttype/json) → [ContentType](contenttype-class)

::: {.features}
final
:::

Content type for JSON using UTF-8 encoding.

[text](contenttype/text) → [ContentType](contenttype-class)

::: {.features}
final
:::

Content type for plain text using UTF-8 encoding.

Static Methods
--------------

[parse](contenttype/parse)([String](../dart-core/string-class) value) →
[ContentType](contenttype-class)

::: {.features}
override
:::

Creates a new content type object from parsing a Content-Type header
value. As primary type, sub type and parameter names and values are not
case sensitive all these values will be converted to lower case. Parsing
this string

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/ContentType-class.html>
:::
