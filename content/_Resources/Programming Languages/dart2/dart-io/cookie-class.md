[dart:io](../dart-io/dart-io-library){._links-link}

Cookie class
============

Representation of a cookie. For cookies received by the server as Cookie
header values only [name](cookie/name) and [value](cookie/value)
properties will be set. When building a cookie for the \'set-cookie\'
header in the server and when receiving cookies in the client as
\'set-cookie\' headers all fields can be used.

Constructors
------------

[Cookie](cookie/cookie)([String](../dart-core/string-class) name,
[String](../dart-core/string-class) value)

::: {.constructor-modifier .features}
factory
:::

Creates a new cookie setting the name and value.

[Cookie.fromSetCookieValue](cookie/cookie.fromsetcookievalue)([String](../dart-core/string-class)
value)

::: {.constructor-modifier .features}
factory
:::

Creates a new cookie by parsing a header value from a \'set-cookie\'
header.

Properties {#instance-properties}
----------

[domain](cookie/domain) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

The domain that the cookie applies to.

[expires](cookie/expires) ↔ [DateTime](../dart-core/datetime-class)?

::: {.features}
read / write
:::

The time at which the cookie expires.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[httpOnly](cookie/httponly) ↔ [bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Whether the cookie is only sent in the HTTP request and is not made
available to client side scripts.

[maxAge](cookie/maxage) ↔ [int](../dart-core/int-class)?

::: {.features}
read / write
:::

The number of seconds until the cookie expires. A zero or negative value
means the cookie has expired.

[name](cookie/name) ↔ [String](../dart-core/string-class)

::: {.features}
read / write
:::

The name of the cookie.

[path](cookie/path) ↔ [String](../dart-core/string-class)?

::: {.features}
read / write
:::

The path within the [domain](cookie/domain) that the cookie applies to.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[secure](cookie/secure) ↔ [bool](../dart-core/bool-class)

::: {.features}
read / write
:::

Whether to only send this cookie on secure connections.

[value](cookie/value) ↔ [String](../dart-core/string-class)

::: {.features}
read / write
:::

The value of the cookie.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](cookie/tostring)() → [String](../dart-core/string-class)

::: {.features}
override
:::

Returns the formatted string representation of the cookie. The string
representation can be used for setting the Cookie or \'set-cookie\'
headers

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
<https://api.dart.dev/stable/2.18.5/dart-io/Cookie-class.html>
:::
