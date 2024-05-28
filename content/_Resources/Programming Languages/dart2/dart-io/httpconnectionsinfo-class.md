[dart:io](../dart-io/dart-io-library){._links-link}

HttpConnectionsInfo class
=========================

Summary statistics about an [HttpServer](httpserver-class)s current
socket connections.

Constructors
------------

[HttpConnectionsInfo](httpconnectionsinfo/httpconnectionsinfo)()

Properties {#instance-properties}
----------

[active](httpconnectionsinfo/active) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

Number of active connections where actual request/response processing is
active.

[closing](httpconnectionsinfo/closing) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

Number of connections which are preparing to close.

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[idle](httpconnectionsinfo/idle) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

Number of idle connections held by clients as persistent connections.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[total](httpconnectionsinfo/total) ↔ [int](../dart-core/int-class)

::: {.features}
read / write
:::

Total number of socket connections.

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

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-io/HttpConnectionsInfo-class.html>
:::
