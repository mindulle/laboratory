[dart:io](../dart-io/dart-io-library){._links-link}

HeaderValue class
=================

Representation of a header value in the form:

``` {.language-plaintext data-language="dart"}
value; parameter1=value1; parameter2=value2
```

[HeaderValue](headervalue-class) can be used to conveniently build and
parse header values on this form.

Parameter values can be omitted, in which case the value is parsed as
`null`. Values can be doubled quoted to allow characters outside of the
RFC 7230 token characters and backslash sequences can be used to
represent the double quote and backslash characters themselves.

To build an \"accepts\" header with the value

``` {.language-dart data-language="dart"}
text/plain; q=0.3, text/html
```

use code like this:

``` {.language-dart data-language="dart"}
HttpClientRequest request = ...;
var v = HeaderValue("text/plain", {"q": "0.3"});
request.headers.add(HttpHeaders.acceptHeader, v);
request.headers.add(HttpHeaders.acceptHeader, "text/html");
```

To parse the header values use the [parse](headervalue/parse) static
method.

``` {.language-dart data-language="dart"}
HttpRequest request = ...;
List<String> values = request.headers[HttpHeaders.acceptHeader];
values.forEach((value) {
  HeaderValue v = HeaderValue.parse(value);
  // Use v.value and v.parameters
});
```

An instance of [HeaderValue](headervalue-class) is immutable.

Implementers

:   -   [ContentType](contenttype-class)

Constructors
------------

[HeaderValue](headervalue/headervalue)(\[[String](../dart-core/string-class)
value = \"\",
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)?\> parameters = const {}\])

::: {.constructor-modifier .features}
factory
:::

Creates a new header value object setting the value and parameters.

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[parameters](headervalue/parameters) →
[Map](../dart-core/map-class)\<[String](../dart-core/string-class),
[String](../dart-core/string-class)?\>

::: {.features}
read-only
:::

A map of parameters.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[value](headervalue/value) → [String](../dart-core/string-class)

::: {.features}
read-only
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

[toString](headervalue/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

Returns the formatted string representation in the form:

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

[parse](headervalue/parse)([String](../dart-core/string-class) value, {[String](../dart-core/string-class) parameterSeparator = \";\", [String](../dart-core/string-class)? valueSeparator, [bool](../dart-core/bool-class) preserveBackslash = false}) → [HeaderValue](headervalue-class)
:   Creates a new header value object from parsing a header value string
    with both value and optional parameters.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HeaderValue-class.html>
:::
