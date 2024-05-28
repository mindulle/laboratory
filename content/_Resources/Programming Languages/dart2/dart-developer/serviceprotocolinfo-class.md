[dart:developer](../dart-developer/dart-developer-library){._links-link}

ServiceProtocolInfo class
=========================

Service protocol is the protocol that a client like the Observatory
could use to access the services provided by the Dart VM for debugging
and inspecting Dart programs. This class encapsulates the version number
and Uri for accessing this service.

Constructors
------------

[ServiceProtocolInfo](serviceprotocolinfo/serviceprotocolinfo)([Uri](../dart-core/uri-class)?
serverUri)

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[majorVersion](serviceprotocolinfo/majorversion) →
[int](../dart-core/int-class)

::: {.features}
final
:::

The major version of the protocol. If the running Dart environment does
not support the service protocol, this is 0.

[minorVersion](serviceprotocolinfo/minorversion) →
[int](../dart-core/int-class)

::: {.features}
final
:::

The minor version of the protocol. If the running Dart environment does
not support the service protocol, this is 0.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[serverUri](serviceprotocolinfo/serveruri) →
[Uri](../dart-core/uri-class)?

::: {.features}
final
:::

The Uri to connect to the debugger client hosted by the service. If the
web server is not running, this will be null.

[serverWebSocketUri](serviceprotocolinfo/serverwebsocketuri) →
[Uri](../dart-core/uri-class)?

::: {.features}
read-only
:::

The Uri to connect to the service via web socket. If the web server is
not running, this will be null.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](serviceprotocolinfo/tostring)() →
[String](../dart-core/string-class)

::: {.features}
override
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
<https://api.dart.dev/stable/2.18.5/dart-developer/ServiceProtocolInfo-class.html>
:::
