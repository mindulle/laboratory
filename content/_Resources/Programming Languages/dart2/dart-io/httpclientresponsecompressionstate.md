[dart:io](../dart-io/dart-io-library){._links-link}

HttpClientResponseCompressionState enum
=======================================

Enum that specifies the compression state of the byte stream of an
[HttpClientResponse](httpclientresponse-class).

The values herein allow callers to answer the following questions as
they pertain to an [HttpClientResponse](httpclientresponse-class):

-   Can the value of the response\'s `Content-Length` HTTP header be
    trusted?
-   Does the caller need to manually decompress the response\'s byte
    stream?

This enum is accessed via the
[HttpClientResponse.compressionState](httpclientresponse/compressionstate)
value.

Inheritance

:   -   [Object](../dart-core/object-class)
    -   [Enum](../dart-core/enum-class)
    -   HttpClientResponseCompressionState

Annotations

:   -   \@Since(\"2.4\")

Constructors
------------

[HttpClientResponseCompressionState](httpclientresponsecompressionstate/httpclientresponsecompressionstate)()

::: {.constructor-modifier .features}
const
:::

Values
------

notCompressed → const [HttpClientResponseCompressionState](httpclientresponsecompressionstate)

:   The body of the HTTP response was received and remains in an
    uncompressed state.

    In this state, the value of the `Content-Length` HTTP header, if
    specified (non-negative), should match the number of bytes produced
    by the response\'s byte stream.

    <div>

    `HttpClientResponseCompressionState()`

    </div>

decompressed → const [HttpClientResponseCompressionState](httpclientresponsecompressionstate)

:   The body of the HTTP response was originally compressed, but by
    virtue of the [HttpClient.autoUncompress](httpclient/autouncompress)
    configuration option, it has been automatically uncompressed.

    HTTP headers are not modified, so when a response has been
    uncompressed in this way, the value of the `Content-Length` HTTP
    header cannot be trusted, as it will contain the compressed content
    length, whereas the stream of bytes produced by the response will
    contain uncompressed bytes.

    <div>

    `HttpClientResponseCompressionState()`

    </div>

compressed → const [HttpClientResponseCompressionState](httpclientresponsecompressionstate)

:   The body of the HTTP response contains compressed bytes.

    In this state, the value of the `Content-Length` HTTP header, if
    specified (non-negative), should match the number of bytes produced
    by the response\'s byte stream.

    If the caller wishes to manually uncompress the body of the
    response, it should consult the value of the `Content-Encoding` HTTP
    header to see what type of compression has been applied. See
    [tools.ietf.org/html/rfc2616\#section-14.11](https://tools.ietf.org/html/rfc2616#section-14.11)
    for more information.

    <div>

    `HttpClientResponseCompressionState()`

    </div>

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[index](../dart-core/enum/index) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

A numeric identifier for the enumerated value.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

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

Constants
---------

[values](httpclientresponsecompressionstate/values-constant) → const [List](../dart-core/list-class)\<[HttpClientResponseCompressionState](httpclientresponsecompressionstate)\>
:   A constant List of the values in this enum, in order of their
    declaration.
    <div>

    `[notCompressed, decompressed, compressed]`

    </div>

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpClientResponseCompressionState.html>
:::
